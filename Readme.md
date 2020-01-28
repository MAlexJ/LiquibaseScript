**DataBase** <br>
ver: oracle-12c-ee

**Docker container**<br>
https://hub.docker.com/r/absolutapps/oracle-12c-ee

**Connect to DB**<br> 
sqlplus sys as sysdba

**Create a new user**<br>
Run SQL:
1. CREATE USER malex IDENTIFIED BY pasw1234;
2. GRANT ALL PRIVILEGES TO malex;

**Viewing Tables**<br>
Run SQL:

1. Viewing Tables Owned by Current user <br>
SELECT * FROM user_tables;
 
2. Viewing Tables Accessible by Current User <br>
SELECT * FROM all_tables; <br>
SELECT owner, table_name FROM all_tables;

**Connect to Oracle DB via JDBC driver**<br>
https://mkyong.com/jdbc/connect-to-oracle-db-via-jdbc-driver-java/

**How to add Oracle JDBC driver in your Maven local repository**<br>
https://mkyong.com/maven/how-to-add-oracle-jdbc-driver-in-your-maven-local-repository/

**DDL SQL**<br>
-- Create Table<br>
CREATE TABLE CD_FILES ( <br>
DEPARTMENT VARCHAR(50) NOT NULL, <br>
BACKUP_SET VARCHAR(50) NOT NULL,  <br>
FULL_PATH VARCHAR(500) NOT NULL, <br>
CD_PATH VARCHAR(300) NOT NULL, <br>
"DISK" VARCHAR(50) NOT NULL); <br>

-- Drop Table<br>
DROP TABLE CD_FILES;
DROP TABLE DATABASECHANGELOG;
DROP TABLE DATABASECHANGELOGLOCK;

OR <br>

BEGIN
FOR c IN (SELECT table_name FROM user_tables) LOOP
EXECUTE IMMEDIATE ('DROP TABLE "' || c.table_name || '" CASCADE CONSTRAINTS');
END LOOP;
FOR s IN (SELECT sequence_name FROM user_sequences) LOOP
EXECUTE IMMEDIATE ('DROP SEQUENCE ' || s.sequence_name);
END LOOP;
END;