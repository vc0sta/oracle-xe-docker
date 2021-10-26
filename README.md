# Oracle Database Container

Just a docker-compose file based on [official Oracle docker images repo](https://github.com/oracle/docker-images/blob/main/OracleDatabase/SingleInstance/README.md#running-oracle-database-18c-express-edition-in-a-container)

Before starting up the database, change the password in **docker-compose.yml**:
```yaml
    environment: 
      - ORACLE_PWD=<your password>
```

Then run:
```sh
docker-compose up
```

To access sqlplus use:
```sh
docker-compose exec database sqlplus sys/<your password>@//localhost:1521/XE as sysdba
docker-compose exec database sqlplus system/<your password>@//localhost:1521/XE
docker-compose exec database sqlplus pdbadmin/<your password>@//localhost:1521/XEPDB1
```