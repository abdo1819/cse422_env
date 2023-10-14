# oracle database environment
enviroment setup for database course CSE422
using oracle 11g express edition



# prerequests
* git [[donwload](https://git-scm.com/downloads)]
* docker [[donwload](https://www.docker.com/products/docker-desktop/)]
* vs code [[download](https://code.visualstudio.com/Download)]
* sqlcl [[donwload](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/download/)]

# database environment
1. clone this repo
    ```bash
    git clone https://github.com/abdo1819/cse422_env
    ```
2. start docker container 
    * switch to repo directory
    ```bash
    cd cse422_env
    docker-compose up
    ```
 

8. connect with vscode to execute your queries
    * install [oracle extention](https://marketplace.visualstudio.com/items?itemName=Oracle.oracledevtools)
    * add coneection info
   ```
   Port number : 49161
   Service name : xe
   Role : Default
   User name : HR
   Password : hr
   
   ```
    ![image](https://user-images.githubusercontent.com/13080469/196804794-5ed8d6c7-b6c0-40a2-816d-1de5846a416b.png)
    * run your query
    * create .sql file
    * make sure current language is set to `Oracle-SQL and PLSQL`
    ```sql
    select MAX(SALARY) from EMPLOYEES ;
    ```
    ```
     MAX(SALARY)
    ______________
         24000
    ```
    * ![image](https://user-images.githubusercontent.com/13080469/196804981-5630535d-bdba-4943-bb5e-a34043b231bc.png)

    
    
     

# troubleshooting
## hr schame is locked
3. connect to database
    * switch to sqlcl\bin directory [⬆️ from prerequests](#prerequests))
    ```
    cd sqlcl\bin
    ```
    * connect to sys schema
    ```
    .\sql sys/oracle@localhost:49161/xe as sysdba
    alter user hr account unlock;
    ```

