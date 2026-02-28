# Experiment 1 – Table Operations on EMPLOYEE_MASTER

## 🎯 Objective
To perform table creation, deletion, update, alteration, and drop operations using EMPLOYEE_MASTER table.

---

## 1️⃣ Create EMPLOYEE_MASTER Table Using EMPLOYEE

```sql
CREATE TABLE EMPLOYEE_MASTER AS
SELECT * FROM EMPLOYEE;
```

---

## 2️⃣ Delete All Records from EMPLOYEE_MASTER Where DeptNo is 10

```sql
DELETE FROM EMPLOYEE_MASTER
WHERE deptno = 10;
```

---

## 3️⃣ Update Salary by 10% for DeptNo 20 in EMPLOYEE_MASTER

```sql
UPDATE EMPLOYEE_MASTER
SET sal = sal + (sal * 0.10)
WHERE deptno = 20;
```

---

## 4️⃣ Alter sal Column Size to DECIMAL(10,2) in EMPLOYEE_MASTER

```sql
ALTER TABLE EMPLOYEE_MASTER
MODIFY sal DECIMAL(10,2);
```

---

## 5️⃣ Drop EMPLOYEE_MASTER Table

```sql
DROP TABLE EMPLOYEE_MASTER;
```

---

## ✅ Conclusion
Successfully performed table creation, deletion, update, alteration, and drop operations on EMPLOYEE_MASTER table.
