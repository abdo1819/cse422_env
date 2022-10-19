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
    * switch to sqlcl\bin directory (downloaded above [⬆️](#prerequests))
    * connect to hr schema
    ```
    cd sqlcl\bin
    ```
    
    ```bash
    .\sql hr/hr@localhost:49161/xe
    ```
 6. try some action
    ```sql
    select MAX(SALARY) from EMPLOYEES ;
    ```
    
    ```
     MAX(SALARY)
    ______________
         24000
    ```

7. [optional] connect with vscode to exucte your queries
    * install [oracle extention](https://marketplace.visualstudio.com/items?itemName=Oracle.oracledevtools)
    * add coneection info
    ![image](https://user-images.githubusercontent.com/13080469/196804794-5ed8d6c7-b6c0-40a2-816d-1de5846a416b.png)
    * run your query
    * ![image](https://user-images.githubusercontent.com/13080469/196804981-5630535d-bdba-4943-bb5e-a34043b231bc.png)

     

# troubleshooting
## hr schame is locked
* connect to sys schema
    ```
    .\sql sys/oracle@localhost:49161/xe as sysdba
    alter user hr account unlock;
    ```

