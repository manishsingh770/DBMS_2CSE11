# Experiment 6 – Date Functions & DECODE

## 🎯 Objective
To perform date calculations, formatting, conditional decoding, and advanced queries using the EMPLOYEE and DEPARTMENT tables.

---

## 1️⃣ Display empno, ename, deptno from EMPLOYEE table.
Instead of department number, display the related department name (Using DECODE).

```sql
SELECT empno,
       ename,
       DECODE(deptno,
              10, 'RESEARCH',
              20, 'ACCOUNTING',
              30, 'SALES',
              40, 'OPERATIONS') AS department_name
FROM EMPLOYEE;
```

---

## 2️⃣ Display your age in days.

```sql
SELECT TRUNC(SYSDATE - DATE '2007-10-03') AS age_in_days
FROM dual;
```

---

## 3️⃣ Display your age in months.

```sql
SELECT TRUNC(MONTHS_BETWEEN(SYSDATE, DATE '2007-10-03')) AS age_in_months
FROM dual;
```

---

## 4️⃣ Display the current date as  
*15th August Friday Nineteen Ninety-Seven* (format example).

```sql
SELECT TO_CHAR(SYSDATE,
       'DDth Month Day YYYY',
       'NLS_DATE_LANGUAGE=ENGLISH') AS formatted_date
FROM dual;
```

---

## 5️⃣ Display the following output for each row from EMPLOYEE table.

```sql
SELECT ename || ' earns ' || sal || ' per month' AS employee_salary_info
FROM EMPLOYEE;
```

---

## 6️⃣ Display:
*Scott has joined the company on Wednesday 13th August Nineteen Ninety*

```sql
SELECT ename || ' has joined the company on ' ||
       TO_CHAR(hiredate, 'Day DDth Month YYYY',
       'NLS_DATE_LANGUAGE=ENGLISH') AS joining_info
FROM EMPLOYEE
WHERE ename = 'SCOTT';
```

---

## 7️⃣ Find the date for nearest Saturday after current date.

```sql
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') AS next_saturday
FROM dual;
```

---

## 8️⃣ Display current time.

```sql
SELECT TO_CHAR(SYSDATE, 'HH:MI:SS AM') AS current_time
FROM dual;
```

---

## 9️⃣ Display the date three months before the current date.

```sql
SELECT ADD_MONTHS(SYSDATE, -3) AS date_before_three_months
FROM dual;
```

---

## 🔟 Display those employees who joined the company in the month of December.

```sql
SELECT ename, hiredate
FROM EMPLOYEE
WHERE TO_CHAR(hiredate, 'MON') = 'DEC';
```

---

## 1️⃣1️⃣ Display those employees whose
first 2 characters of hiredate = last 2 characters of salary.

```sql
SELECT ename, hiredate, sal
FROM EMPLOYEE
WHERE SUBSTR(TO_CHAR(hiredate, 'DD'), 1, 2) =
      SUBSTR(TO_CHAR(sal), -2);
```

---

## 1️⃣2️⃣ Display those employees whose 10% of salary
is equal to the year of joining.

```sql
SELECT ename, sal, hiredate
FROM EMPLOYEE
WHERE sal * 0.10 = TO_NUMBER(TO_CHAR(hiredate, 'YYYY'));
```

---

## 1️⃣3️⃣ Display those employees who joined the company before 15th of the month.

```sql
SELECT ename, hiredate
FROM EMPLOYEE
WHERE TO_NUMBER(TO_CHAR(hiredate, 'DD')) < 15;
```

---

## 1️⃣4️⃣ Display those employees who has joined before 15th of the month.

```sql
SELECT ename, hiredate
FROM EMPLOYEE
WHERE EXTRACT(DAY FROM hiredate) < 15;
```

---

## 1️⃣5️⃣ Display those employees whose joining DATE is available in deptno.

```sql
SELECT ename, hiredate, deptno
FROM EMPLOYEE
WHERE TO_CHAR(hiredate, 'DD') = TO_CHAR(deptno);
```

---

## ✅ Conclusion
Successfully executed SQL queries involving DECODE, date arithmetic, date formatting, and conditional retrieval using the EMPLOYEE and DEPARTMENT tables.
