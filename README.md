# SQL_in_one
# What is DataBase?
-> A database is a software that storers data in organized manner.
A database is an organized collection of structured information, or data, typically stored electronically in a computer system.
Computer databases typically store aggregations of data records or files that contain information, such as sales transactions, customer data, financials and product information.

![](https://i0.wp.com/ubiq.co/database-blog/wp-content/uploads/2020/10/enable-mysql-replication.png?resize=730%2C410&ssl=1)

# What is MySQL?
-> MySQL is a DataBase Software used to handle data in relational manner.


Relational manner: follows a pattern (In the form of tables) we can connect tables in relational database.

![](https://www.pragimtech.com/blog/contribute/article_images/2220211210231003/what-is-a-relational-database.jpg)

 Data can be accesed by queires. it works on theprinciple of request and get
![](https://programmer.group/images/article/4afb276e564fd636f0486cd37abeed48.jpg)

# Download MySQL
Download MySQL Software: https://dev.mysql.com/downloads/mysql/

# Table Operations
1. Show databases : used to view databases which arre present in the database server
 ```show databases; ```
 
2. To create a database : create database [database_name]
```create database employee```

3. To use/select a particular database : use [database_name]
```use employee```

4. To delete a database we make use of drop : drop database [database_name]
```drop database employee```

5. To create a table we have to make note of two things first create a ```table``` and ```columns```
create table [table_name] (col 1,col 2,col 3,col 4 ,....)

```create table user(id int(15) primary key, name varchar(150) not null, city varchar(150));```

# Primary key:  
A primary key is the column or columns that contain values that uniquely identify each row in a table
I used primary to key to make it unique to identify the user as an unique entry

6. Suoppose you forgot what was the column name and the property of the table thn you can make use of desc for describing the table. desc [table_name]; 
 ```desc user;```
```
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| id    | int          | NO   | PRI | NULL    |       |
| name  | varchar(150) | NO   |     | NULL    |       |
| city  | varchar(150) | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
```

7. Type ```show tables;``` to view the table that you've created
```
+--------------------+
| Tables_in_employee |
+--------------------+
| user               |
+--------------------+
```
8. To drop a table just like the database we have drop earlier we make use of:  drop table [table_name] and the table will get deleted.
```drop table user;```

9. To Rename a table name we make use of alter: alter table [old_name] rename to [new_name];
 ```alter table user rename to student;```
 
 check the table name ```show tables```;
 
 10. To delete all the records of the table we make use of truncate command
 NOTE: ONLY THE DATA IN THE  TABLE WILL GET DELETED NOT THE TABLE!
 ```truncate table student;```
 
 
