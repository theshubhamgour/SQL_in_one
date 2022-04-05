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

# Database Operations
1. Show databases : used to view databases which arre present in the database server
 ```show databases; ```
 
2. To create a database : create database [database_name]
```create database employee```

3. To use/select a particular database : use [database_name]
```use employee```

4. To delete a database we make use of drop : drop database [database_name]
```drop database employee```

# Table operations
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
 
 10. To delete all the records of the table we make use of truncate command.
 NOTE: ONLY THE DATA IN THE  TABLE WILL GET DELETED NOT THE TABLE!
 ```truncate table student;```
 
 11. To feed data into table we makw use of ```insert into``` command: insert into [table_name](id,name,city) values(id(in int),name(in char),city(in char));
 ```insert into student(id,name,city) values(15,"Aditya Jain","Nagpur");```
 
 12. In order to check the entry we just made we makw use of : select * from [table_name];
 ```select * from student;```
 ```
 +----+-------------+--------+
| id | name        | city   |
+----+-------------+--------+
| 15 | Aditya Jain | Nagpur |
+----+-------------+--------+
```
13. To add a column in table: alter table [table_name] add [col_name];
```alter table student add country varchar(50);```

14. To update entry we make use of : update [table_name] set [col_name] = "Value";
NOTE: IF YOU RUN THIS COMMAND ```update student set country = "India";``` ENTIRE COLUMN OF COUNTRY WILL TURN INTO INDIA.

Type: ``` select * from student; ``` to check the entry
```
+----+-------------+--------+---------+
| id | name        | city   | country |
+----+-------------+--------+---------+
| 15 | Aditya Jain | Nagpur | India   |
+----+-------------+--------+---------+
```

15. Lets add more data in the table: 
```
 insert into student(id,name,city) values(10, "Shubham","Nagpur");
 ```
 16. In Order to add data to a specifiic id we make use of where:
 
``` update student set country= "India" where id = 10;
    update student set country= "Saudi Arab" where id = 15;
```

Type ```select * from student```
```
+----+-------------+--------+------------+
| id | name        | city   | country    |
+----+-------------+--------+------------+
| 10 | Shubham     | Nagpur | India      |
| 15 | Aditya Jain | Nagpur | Saudi Arab |
+----+-------------+--------+------------+
```

17. For inserting multiple valuies at once: 
```
insert into student values (1,"Pradhynesh","Bhandara","Delhi"),
                           (2,"Shubham Bedarkar","Amravati","MP"),
                           (3,"Neha","Berlin","Germany"),  
                           (4,"Sayali","Mathura","India");
```

type: ```select * from student;``` to check the entry we made just now to ensure everything is going properly.
```

+----+------------------+----------+------------+
| id | name             | city     | country    |
+----+------------------+----------+------------+
|  1 | Pradhynesh       | Bhandara | Delhi      |
|  2 | Shubham Bedarkar | Amravati | MP         |
|  3 | Neha             | Berlin   | Germany    |
|  4 | Sayali           | Mathura  | India      |
| 10 | Shubham          | Nagpur   | India      |
| 15 | Aditya Jain      | Nagpur   | Saudi Arab |
+----+------------------+----------+------------+

```
18. To delete the data from the table for a specific user: delete from [table_name] where [col_name]=[value]

```
delete from student where id=15;
```

# Clauses
For  sorting dat we makew use opf clauses
19. where: 
```select * from student where city = "Nagpur";```
```
+----+---------+--------+---------+
| id | name    | city   | country |
+----+---------+--------+---------+
| 10 | Shubham | Nagpur | India   |
+----+---------+--------+---------+
```
Method 2: to sort it with just a particular information we make use of below command:
```
 select name,city,country from student where country ="india";
```
```
+---------+---------+---------+
| name    | city    | country |
+---------+---------+---------+
| Sayali  | Mathura | India   |
| Shubham | Nagpur  | India   |
+---------+---------+---------+
```
20: Alias : Used to changw the name temporary
```
select name as "USERNAME" , country as "HOMELAND" from student;
```
```
+------------------+----------+
| USERNAME         | HOMELAND |
+------------------+----------+
| Pradhynesh       | Delhi    |
| Shubham Bedarkar | MP       |
| Neha             | Germany  |
| Sayali           | India    |
| Shubham          | India    |
+------------------+----------+
```
21: Distinct : Do not repeat same values again and again
```
select distinct (country) from student;
```
Above and below command will give same output
```
select distinct country from student;
```
```
+---------+
| country |
+---------+
| Delhi   |
| MP      |
| Germany |
| India   |
+---------+
```
