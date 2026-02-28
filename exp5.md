# Experiment 5 – Aggregate & String Functions

## 🎯 Objective
To perform aggregate functions and string operations on the EMPLOYEE table.

---

## 1️⃣ Display the total number of employees working in the company.

```sql
SELECT COUNT(*) AS total_employees
FROM EMPLOYEE;
```

---

## 2️⃣ Display the total salary being paid to all employees.

```sql
SELECT SUM(sal) AS total_salary
FROM EMPLOYEE;
```

---

## 3️⃣ Display the maximum salary from EMPLOYEE table.

```sql
SELECT MAX(sal) AS maximum_salary
FROM EMPLOYEE;
```

---

## 4️⃣ Display the minimum salary from EMPLOYEE table.

```sql
SELECT MIN(sal) AS minimum_salary
FROM EMPLOYEE;
```

---

## 5️⃣ Display the average salary from EMPLOYEE table.

```sql
SELECT AVG(sal) AS average_salary
FROM EMPLOYEE;
```

---

## 6️⃣ Display the maximum salary being paid to clerk.

```sql
SELECT MAX(sal) AS max_clerk_salary
FROM EMPLOYEE
WHERE job = 'CLERK';
```

---

## 7️⃣ Display the maximum salary being paid in dept no 20.

```sql
SELECT MAX(sal) AS max_salary_dept20
FROM EMPLOYEE
WHERE deptno = 20;
```

---

## 8️⃣ Display the minimum salary paid to any salesman.

```sql
SELECT MIN(sal) AS min_salesman_salary
FROM EMPLOYEE
WHERE job = 'SALESMAN';
```

---

## 9️⃣ Display the average salary drawn by managers.

```sql
SELECT AVG(sal) AS avg_manager_salary
FROM EMPLOYEE
WHERE job = 'MANAGER';
```

---

## 🔟 Display the total salary drawn by analysts working in dept no 40.

```sql
SELECT SUM(sal) AS total_analyst_salary
FROM EMPLOYEE
WHERE job = 'ANALYST'
AND deptno = 40;
```

---

## 1️⃣1️⃣ Display the names of employees in uppercase.

```sql
SELECT UPPER(ename) AS uppercase_name
FROM EMPLOYEE;
```

---

## 1️⃣2️⃣ Display the names of employees in lowercase.

```sql
SELECT LOWER(ename) AS lowercase_name
FROM EMPLOYEE;
```

---

## 1️⃣3️⃣ Display the names of employees in proper case.

```sql
SELECT CONCAT(UPPER(LEFT(ename, 1)), LOWER(SUBSTRING(ename, 2))) AS proper_case_name
FROM EMPLOYEE;
```

---

## 1️⃣4️⃣ Display the length of your name using appropriate function.

```sql
SELECT LENGTH('MANISH') AS name_length;
```

---

## 1️⃣5️⃣ Display the length of all employee names.

```sql
SELECT ename, LENGTH(ename) AS name_length
FROM EMPLOYEE;
```

---

## ✅ Conclusion
Successfully applied aggregate functions and string functions on the EMPLOYEE table.
