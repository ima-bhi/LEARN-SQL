````markdown
# 📘 Day 1 - MySQL Basics

## 🔍 Show All Databases

```sql
SHOW DATABASES;
````

**Output:**

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```

---

## 🛠️ Create a New Database

```sql
CREATE DATABASE MyCat;
```

**Confirmation:**

```
Query OK, 1 row affected (0.01 sec)
```

---

## 📂 Show Databases Again

```sql
SHOW DATABASES;
```

**Output:**

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mycat              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```

---

## 🔄 Use the Created Database

```sql
USE mycat;
```

**Output:**

```
Database changed
```

---

## ✅ Confirm Current Database

```sql
SELECT DATABASE();
```

**Output:**

```
+------------+
| DATABASE() |
+------------+
| mycat      |
+------------+
```

---

## 🐱 Create Table `cats`

```sql
CREATE TABLE cats (
    name VARCHAR(100),
    age INT
);
```

**Output:**

```
Query OK, 0 rows affected (0.06 sec)
```

---

## 📄 Check Data in `cats` Table

```sql
SELECT * FROM cats;
```

**Output:**

```
Empty set (0.01 sec)
```

---

## 🧾 Describe `cats` Table (Using `DESC`)

```sql
DESC cats;
```

**Output:**

```
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | YES  |     | NULL    |       |
| age   | int          | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
```

---

## 📋 Show All Tables

```sql
SHOW TABLES;
```

**Output:**

```
+-----------------+
| Tables_in_mycat |
+-----------------+
| cats            |
+-----------------+
```

---

## 📚 Show Columns of `cats` Table

```sql
SHOW COLUMNS FROM cats;
```

**Output:**

```
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | YES  |     | NULL    |       |
| age   | int          | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
```

---

## ❌ Drop Table `cats`

```sql
DROP TABLE cats;
```

**Output:**

```
Query OK, 0 rows affected (0.04 sec)
```

---

## 📭 Confirm Table Removal

```sql
SHOW TABLES;
```

**Output:**

```
Empty set (0.00 sec)
```

---

## 🧁 Create Table `pastries`

```sql
CREATE TABLE pastries (
    name VARCHAR(50),
    quantity INT
);
```

**Output:**

```
Query OK, 0 rows affected (0.04 sec)
```

---

## 📋 Show All Tables Again

```sql
SHOW TABLES;
```

**Output:**

```
+-----------------+
| Tables_in_mycat |
+-----------------+
| pastries        |
+-----------------+
```

---

## 📑 Describe `pastries` Table

```sql
DESC pastries;
```

**Output:**

```
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| name     | varchar(50) | YES  |     | NULL    |       |
| quantity | int         | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
```

---

## 🗑️ Drop Table `pastries`

```sql
DROP TABLE pastries;
```

**Output:**

```
Query OK, 0 rows affected (0.03 sec)
```

---

## ✅ Summary of Day 1

| Command             | Description                           |
| ------------------- | ------------------------------------- |
| `SHOW DATABASES`    | Lists all databases                   |
| `CREATE DATABASE`   | Creates a new database                |
| `USE db_name`       | Selects a database to work in         |
| `SELECT DATABASE()` | Displays the current database in use  |
| `CREATE TABLE`      | Creates a table                       |
| `DESC table_name`   | Describes the structure of a table    |
| `SHOW TABLES`       | Lists all tables in current database  |
| `SHOW COLUMNS`      | Lists columns and metadata of a table |
| `DROP TABLE`        | Deletes a table                       |

---

🗓️ **End of Day 1 Practice**

```

Let me know if you'd like to split it by sections, add screenshots, or convert this to a PDF!
```
