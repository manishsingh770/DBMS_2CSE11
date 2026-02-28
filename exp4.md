# Experiment 4 – Conditional Queries and Salary Calculations

## 🎯 Objective
To perform conditional filtering, salary calculations, updates, and pattern-based queries on the EMPLOYEE table.

---

## 1️⃣ Display employees who joined before 30th June 1980 or after 31st Dec 1981.

```sql
SELECT ename, hiredate
FROM EMPLOYEE
WHERE hiredate < '1980-06-30'
OR hiredate > '1981-12-31';
```

---

## 2️⃣ Display the names of employees whose second alphabet is 'A'.

```sql
SELECT ename
FROM EMPLOYEE
WHERE ename LIKE '_A%';
```

---

## 3️⃣ Display the names of employees whose name is exactly five characters long.

```sql
SELECT ename
FROM EMPLOYEE
WHERE LENGTH(ename) = 5;
```

---

## 4️⃣ Display the names of employees whose second alphabet is 'A' (Using SUBSTRING).

```sql
SELECT ename
FROM EMPLOYEE
WHERE SUBSTRING(ename, 2, 1) = 'A';
```

---

## 5️⃣ Display the names of employees who are not working as salesman, clerk or analyst.

```sql
SELECT ename
FROM EMPLOYEE
WHERE job NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
```

---

## 6️⃣ Display employee name along with annual salary (sal * 12). Highest salary should appear first.

```sql
SELECT ename, sal * 12 AS annual_salary
FROM EMPLOYEE
ORDER BY annual_salary DESC;
```

---

## 7️⃣ Display name, sal, hra, da, pf and total salary for each employee.

- HRA = 15% of sal  
- DA = 10% of sal  
- PF = 5% of sal  
- Total Salary = (sal + hra + da) - pf  

```sql
SELECT ename,
       sal,
       sal * 0.15 AS hra,
       sal * 0.10 AS da,
       sal * 0.05 AS pf,
       (sal + (sal * 0.15) + (sal * 0.10)) - (sal * 0.05) AS total_salary
FROM EMPLOYEE;
```

---

## 8️⃣ Update salary by 10% increment for employees not eligible for commission.

sql
UPDATE EMPLOYEE
SET sal = sal + (sal * 0.10)
WHERE comm IS NULL;
```

---

## 9️⃣ Display employees whose salary is more than 3000 after giving 20% increment.

sql
SELECT ename, sal * 1.20 AS increased_salary
FROM EMPLOYEE
WHERE sal * 1.20 > 3000;
```

---

## 🔟 Display employees whose salary contains at least 3 digits.

```sql
SELECT ename, sal
FROM EMPLOYEE
WHERE sal >= 100;
```

---

## ✅ Conclusion
Successfully executed conditional filtering, salary calculations, updates, and pattern-based SQL queries on the EMPLOYEE table.
