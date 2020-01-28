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