# Experiment 9 – Advanced Queries & Aggregations
**Date:** 02-04-2026

## 🎯 Objective
To apply SQL queries using subqueries, joins, and aggregate functions to retrieve and analyze employee data based on salary conditions, job roles, and department information.
___

## 1. Display the name of emp name who earns highest salary.
## 2.isplay the employee number and name of employee working as clerk and earning highest salary among clerks.
## 3. Display the names of the salesman who earns a salary more than the highest salary of any clerk.
## 4. Display the names of clerks who earn salary more than that of james of that of sal lesser than that of scott
## 5. Display the names of employees who earn a sal more than that of james or that of salary greater than that of scott.
## 6. Display the names of the employees who earn highest salary in their respective departments.
## 7. Display the names of employees who earn highest salaries in their respective job groups.
## 8. Display the employee names who are working in accounting dept.
## 9. Display the employee names who are working in mumbai.
## 10. Display the job groups having total salary greater than the maximum salary for managers.

## 1. Display the name of emp name who earns highest salary.
```sql
SELECT ename FROM EMPLOYEE
WHERE sal =(SELECT MAX(sal) FROM EMPLOYEE);
```

## 2. Display the employee number and name of employee working as clerk and earning highest salary among clerks.
```sql
SELECT ename, empno FROM EMPLOYEE WHERE job = 'CLERK' AND sal=(SELECT MAX(sal) FROM EMPLOYEE WHERE job = 'CLERK');
```

## 3. Display the names of the salesman who earns a salary more than the highest salary of any clerk.
```sql
SELECT ename, empno FROM EMPOYEE
WHERE job = 'SALESMAN' AND sal > (SELECT MAX(sal) FROM EMPLOYEE WHERE job = 'CLERK');
```

## 4. Display the names of clerks who earn salary more than that of james of that of sal lesser than that of scott
```sql
SELECT ename FROM EMPLOYEE
WHERE Job = 'CLERK'
AND sal > (SELECT sal FROM EMPLOYEE WHERE ename = 'JAMES')
AND sal < (SELECT sal FROM EMPLOYEE WHERE ename = 'SCOTT');
```

## 5. Display the names of employees who earn a sal more than that of james or that of salary greater than that of scott.
```sql
SELECT ename FROM EMPLOYEE
WHERE sal > (SELECT sal FROM EMPLOYEE WHERE ename = 'JAMES')
OR sal < (SELECT sal FROM EMPLOYEE WHERE ename = 'SCOTT');
```

## 6. Display the names of the employees who earn highest salary in their respective departments.
```sql
SELECT ename, deptno FROM EMPLOYEE e
WHERE sal = (SELECT MAX(sal) FROM EMPLOYEE e2
WHERE e.deptno = e2.deptno);
```

## 7. Display the names of employees who earn highest salaries in their respective job groups.
```sql
SELECT ename, job FROM EMPLOYEE e
WHERE sal = (SELECT MAX(SAL) FROM EMPLOYEE
WHERE e.job = job);
```

## 8. Display the employee names who are working in accounting dept.
```sql
SELECT ENAME FROM EMPLOYEE 
WHERE deptno = (SELECT deptno FROM dept 
WHERE dname = 'ACCOUNTING');
```

## 9. Display the employee names who are working in mumbai.
```sql
SELECT ename
FROM EMPLOYEE
WHERE deptno IN (
SELECT deptno
FROM dept
WHERE location = 'mumbai');
```

## 10. Display the job groups having total salary greater than the maximum salary for managers.
```sql
SELECT job FROM EMPLOYEE
GROUP BY Job
HAVING SUM(sal) > (SELECT MAX(sal) FROM EMPLOYEE
WHERE job = 'MANAGER');
```


