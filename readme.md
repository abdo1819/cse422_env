# oracle database environment
enviroment setup for database course CSE422
using oracle 11g express edition



# prerequests
* git [[donwload](https://git-scm.com/downloads)]
* docker [[donwload](https://www.docker.com/products/docker-desktop/)]
* sqlcl [[donwload](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/download/)]

# database environment
1. clone or download this repo
    > https://github.com/abdo1819/cse422_env
2. start docker container 
    > docker-compose up -d
4. wait little bit or check the container log
    > docker compose logs
3. connect to database
    * switch to sqlcl directory
    * connect to hr schema
    > .\sql hr/hr@localhost:49161/xe


# trouble shouting
## hr schame is locked
* connect to sys schema
    > .\sql sys/oracle@localhost:49161/xe as sysdba
    > alter user hr account unlock;

