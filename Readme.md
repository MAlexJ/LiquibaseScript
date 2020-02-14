**DataBase** <br>
ver: oracle-12c-ee

**Docker container**<br>
https://hub.docker.com/r/absolutapps/oracle-12c-ee

**Connect to DB**<br> 
sqlplus sys as sysdba <br> 
_Log_: sys <br> 
_Role_: sysdba <br> 
_Password_: oracle

**Create a new user**<br>
```
CREATE USER malex IDENTIFIED BY pasw1234;
GRANT ALL PRIVILEGES TO malex;
```

**Viewing Tables**<br>
>Viewing Tables Owned by Current user
```
SELECT * FROM user_tables;
 ```
>Viewing Tables Accessible by Current User 
```
SELECT * FROM all_tables;
SELECT owner, table_name FROM all_tables;
```

**Connect to Oracle DB via JDBC driver**<br>
https://mkyong.com/jdbc/connect-to-oracle-db-via-jdbc-driver-java/

**How to add Oracle JDBC driver in your Maven local repository**<br>
https://mkyong.com/maven/how-to-add-oracle-jdbc-driver-in-your-maven-local-repository/

**DDL SQL**<br>

>Create Table
```
CREATE TABLE CD_FILES (
    DEPARTMENT VARCHAR(50) NOT NULL, 
    BACKUP_SET VARCHAR(50) NOT NULL,  
    FULL_PATH VARCHAR(500) NOT NULL, 
    CD_PATH VARCHAR(300) NOT NULL, 
    "DISK" VARCHAR(50) NOT NULL 
); 
```
>Drop Table
```
DROP TABLE CD_FILES; 
DROP TABLE DATABASECHANGELOG; 
DROP TABLE DATABASECHANGELOGLOCK; 
```
>OR 
```
BEGIN 
    FOR c IN (SELECT table_name FROM user_tables) LOOP 
        EXECUTE IMMEDIATE ('DROP TABLE "' || c.table_name || '" CASCADE CONSTRAINTS'); 
    END LOOP;
    FOR s IN (SELECT sequence_name FROM user_sequences) LOOP 
        EXECUTE IMMEDIATE ('DROP SEQUENCE ' || s.sequence_name); 
    END LOOP; 
END;
```

**Oracle DB backup and restore** <br>

QLDeveloper backup and recovery is integrated in the GUI. 
For download of SQLDeveloper see Oracle SQL Developer It is a free product, 
with active development.

In SQLdeveloper in the View menu select DBA to get access to the dba tools like RMAN and DATAPUMP. 
Very nice tool. Don't forget that the backup files are written by the Oracle database server processes. T
his means that the backups are written on the database server, 
not on your client. Also, currently it just generates a backup script. 
You should run the generated script using RMAN.

**Oracle DB copy** <br>
https://www.youtube.com/watch?v=BkPM3avDFbI