# Experiment 0 – Database Creation

## 🎯 Objective
To create database MANISH and DEPARTMENT & EMPLOYEE tables with inserted values.

---

## 1️⃣ Create Database

```sql
CREATE DATABASE MANISH;
SHOW DATABASES;
```

---

### ✅ Select Database

```sql
USE MANISH;
```

---

## 2️⃣ Create DEPARTMENT Table

```sql
CREATE TABLE DEPARTMENT (
    deptno INT(2) PRIMARY KEY,
    dname VARCHAR(15) NOT NULL
);
```

---

### Describe Table

```sql
DESC DEPARTMENT;
```

---

## 3️⃣ Insert Values into DEPARTMENT

```sql
INSERT INTO DEPARTMENT VALUES
(10, 'RESEARCH'),
(20, 'ACCOUNTING'),
(30, 'SALES'),
(40, 'OPERATIONS');
```

---

### Verify Data

```sql
SELECT * FROM DEPARTMENT;
```

---

## 4️⃣ Create EMPLOYEE Table

```sql
CREATE TABLE EMPLOYEE (
    empno INT(4) PRIMARY KEY,
    ename VARCHAR(20) NOT NULL,
    job VARCHAR(20),
    mgr INT(4),
    hiredate DATE,
    sal INT(10),
    comm INT(7),
    deptno INT(2),
    FOREIGN KEY (deptno) REFERENCES DEPARTMENT(deptno)
);
```

---

### Describe Table

```sql
DESC EMPLOYEE;
```

---

## 5️⃣ Insert Values into EMPLOYEE

```sql
INSERT INTO EMPLOYEE VALUES
(7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20),
(7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30),
(7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 300, 30),
(7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20),
(7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30),
(7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30),
(7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 20),
(7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000, NULL, 20),
(7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 20),
(7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30),
(7876, 'ADAMS', 'CLERK', 7788, '1983-01-12', 1100, NULL, 20),
(7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30),
(7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, NULL, 20),
(7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);
```

---

### Verify Data

```sql
SELECT * FROM EMPLOYEE;
```

---

## ✅ Conclusion
Successfully created database MANISH and tables DEPARTMENT and EMPLOYEE with inserted records.
