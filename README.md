# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
### QUERY:
UPDATE manager
SET SALARY = SALARY + (SALARY *10/100);
### OUTPUT:
![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/4dbad32b-e238-4efa-8601-602774fa7ad1)



### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
delete from manager
 where salary<2750;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/488aecff-1cb4-4a84-bf30-a78b4e71c006)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
 select ename as "Name",salary*12 as "Annual Salary" from manager;
### OUTPUT:
![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/75dd592b-fd6e-4e30-a67b-b8e03c0afbd2)



### Q4)	List the names of Clerks from emp table.
### QUERY:
select ename from manager where designation='clerk';
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/058c40a5-0361-468b-8504-323662f4f697)


### Q5)	List the names of employee who are not Managers.
### QUERY:
select ename from manager where designation <> 'manager';
### OUTPUT:
![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/7c20e12a-df4b-4853-966b-d85170020852)



### Q6)	List the names of employees not eligible for commission.
### QUERY:
select ename from manager where commission=0;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/d7c1ece3-6fb0-4d40-a209-e733bd53640f)


### Q7)	List employees whose name either start or end with ‘s’.
### QUERY:
select ename from manager where ename like '%s' or ename like 's%';
### OUTPUT:
![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/831674ef-0222-4839-a820-56aaa42ddbb8)



### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
 select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/859cbc2f-9a9b-43ba-b215-919dc9c8945b)



### Q9) List the Details of Employees who have joined before 30 Sept 8.
### QUERY:
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/24ea499f-5252-4e12-9175-91b47eadd1ce)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
select ename,deptno,salary from manager order by deptno asc,salary desc;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/ef2ae362-ab6f-4cc6-b8bf-41d2caff7d53)


### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
select ename from manager where deptno not in (30,40,10);
### OUTPUT:


![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/a39e36c3-3d75-408f-81a9-41c27f96ac38)

### Q12) Find number of rows in the table EMP
### QUERY:
select count(*) from manager;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/3fd8c144-3a8a-42aa-a2a6-eb6cbe90cb64)



### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
### OUTPUT:


![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/0a9cdecc-cf51-48fd-ad1f-63bfd083b1da)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
 SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
### OUTPUT:

![image](https://github.com/MarellaDharanesh/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707669/57122a3b-c78c-4f73-84e5-796890db7eb4)
