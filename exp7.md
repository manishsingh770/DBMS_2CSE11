# Experiment 7 – Advanced Queries & Aggregations
**Date:** 14-02-2026

## 🎯 Objective
To perform advanced SQL queries including aggregation, conditional filtering, formatting, and reporting using the `EMPLOYEE` table.

---

## 1️⃣ Compute the number of days remaining in this year.

```sql
SELECT DATEDIFF('2027-01-01', CURDATE()) AS 'Days Remaining';
```

---

## 2️⃣ Find the highest and lowest salaries and the difference between them.

```sql
SELECT MAX(sal) AS highest_salary,
       MIN(sal) AS lowest_salary,
       MAX(sal) - MIN(sal) AS salary_difference
FROM EMPLOYEE;
```

---

## 3️⃣ List employees whose commission is greater than 25% of their salaries.

```sql
SELECT ename, sal, comm
FROM EMPLOYEE
WHERE comm > 0.25 * sal;
```

---

## 4️⃣ Display salary in dollar format.

```sql
SELECT 
    ename,
    CONCAT('$', FORMAT(sal, 2)) AS 'Salary'
FROM EMPLOYEE;
```

---

## 5️⃣ Create a matrix query to display job, salary for that job based on department number, and total salary.

```sql
SELECT job,
       SUM(DECODE(deptno, 10, sal, 0)) AS dept10,
       SUM(DECODE(deptno, 20, sal, 0)) AS dept20,
       SUM(DECODE(deptno, 30, sal, 0)) AS dept30,
       SUM(sal) AS total_salary
FROM EMPLOYEE
GROUP BY job;
```

---

## 6️⃣ Display total number of employees and number hired in each year (1980–1983).

```sql
SELECT 
    COUNT(*) AS 'Total Employees',
    SUM(CASE WHEN YEAR(hiredate) = 1980 THEN 1 ELSE 0 END) AS '1980',
    SUM(CASE WHEN YEAR(hiredate) = 1981 THEN 1 ELSE 0 END) AS '1981',
    SUM(CASE WHEN YEAR(hiredate) = 1982 THEN 1 ELSE 0 END) AS '1982',
    SUM(CASE WHEN YEAR(hiredate) = 1983 THEN 1 ELSE 0 END) AS '1983'
FROM EMPLOYEE;
```

---

## 7️⃣ Find the last Sunday of any month (current month).

```sql
SELECT 
    DATE_SUB(
        LAST_DAY(CURDATE()),
        INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE())) - 1) DAY
    ) AS 'Last Sunday of Month';
```

---

## 8️⃣ Display department numbers and total number of employees in each department.

```sql
SELECT deptno, COUNT(*) AS total_employees
FROM EMPLOYEE
GROUP BY deptno;
```

---

## 9️⃣ Display various jobs and total number of employees in each job group.

```sql
SELECT job, COUNT(*) AS total_employees
FROM EMPLOYEE
GROUP BY job;
```

---

## 🔟 Display department numbers and total salary for each department.

```sql
SELECT deptno, SUM(sal) AS total_salary
FROM EMPLOYEE
GROUP BY deptno;
```

---

## ✅ Conclusion
Successfully executed advanced SQL queries involving aggregation, grouping, formatting, and reporting using the `EMPLOYEE` table.
