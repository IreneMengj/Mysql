1. What is a database?  
A warehouse for storing and managing data  
2. Database features:
- Persistent storage of data. A database is just a file system.
- Convenient storage and management of data
- Use a unified way to operate the database - SQL

3. What is SQL?  
Defines a language to operate on all relational databases. 

4. SQL general syntax  
- SQL can be written in multiple or single lines, ending with a semicolon  
- The SQL of the MYSQL database is case insensitive. You are advised to use uppercase for keywords  
- One-line comment: --  or # 
- Multiline comment：/* */


![image](https://user-images.githubusercontent.com/88880169/221164616-0d8b4891-86e2-48ab-bcf8-d0faeaf3595d.png)


1. DDL(Data Definition Language):operate database and table. 
> CRUD(C:CREATE;R:RETRIVE;U:UPDATE;D:DELETE).    
<b>C:CREATE</b>  
- Create a database:   
  create database + name;   
- Create a database, check that the database does not exist, and create it again.   
 create database if not exists +name;   
- Create the database and specify the character set.    
  create database if not exists +name character set gbk;    
- Create a db4 database, determine whether it exists, and specify the character set gbk.   
  create database if not exists +name character set gbk;
- data type:
  - int
  - double: score double(5,1)
  - date:yyyy-MM-dd
  - datetime:yyyy-MM-dd HH:mm:ss
  - timestamp: yyyy-MM-dd HH:mm:ss  If this field is not assigned in the future, or is null, the current system time is used by default for automatic assignment
  - varchar  
- copy table. 
  create table +name like +Name of the table being replicated;
<b> R:RETRIVE</b>
- Query the name of a database.      
  show databases;
- Query the character set of a database: Queries the creation statement of a database.     
  show create database + name;   
- Query all the table names of a database.  
  show tables;   
- Query table structure.        
  desc + name;   
<b>U:UPDATE</b>.  
- Modify the character set of the database.  
  alter database +name character set +gbk;      
<b>D:DELETE</b>
- Delete database.  
  drop database + name;
- If the database exists, delete it.  
  drop database if exists +name;
- drop tables.  
  drop table +name;  
  drop table if exists +name;
  
