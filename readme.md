# oracle database environment
enviroment setup for database course CSE422
using oracle 11g express edition



# prerequests
* git [[donwload](https://git-scm.com/downloads)]
* docker [[donwload](https://www.docker.com/products/docker-desktop/)]
* sqlcl [[donwload](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/download/)]

# database environment
1. clone or download this repo
    ```bash
    git clone https://github.com/abdo1819/cse422_env
    ```
2. start docker container 
    * switch to repo directory
    ```bash
    cd cse422_env
    docker-compose up -d
    ```
4. wait little bit or check the container log
    ```bash
    docker compose logs
    ```
5. connect to database
    * switch to sqlcl directory (downloaded above [⬆️](#prerequests))
    * connect to hr schema
    ```bash
    .\sql hr/hr@localhost:49161/xe
    ```
 6. try some action
    ```sql
    SELECT JOB_TITLE, DEPARTMENT_NAME, LAST_NAME, START_DATE 
    FROM JOB_HISTORY JOIN JOBS USING (JOB_ID) JOIN DEPARTMENTS 
    USING (DEPARTMENT_ID) JOIN  EMPLOYEES USING (EMPLOYEE_ID) 
    WHERE TO_CHAR(START_DATE,'YYYY') BETWEEN 2000 AND 2005;    
    ``` 
    ```
    JOB_TITLE                   DEPARTMENT_NAME    LAST_NAME    START_DATE
    ___________________________ __________________ ____________ _____________
    Programmer                  IT                 De Haan      13-JAN-01
    Accounting Manager          Accounting         Kochhar      28-OCT-01
    Marketing Representative    Marketing          Hartstein    17-FEB-04
    Public Accountant           Executive          Whalen       01-JUL-02
    ```


# troubleshooting
## hr schame is locked
* connect to sys schema
    ```
    .\sql sys/oracle@localhost:49161/xe as sysdba
    alter user hr account unlock;
    ```

