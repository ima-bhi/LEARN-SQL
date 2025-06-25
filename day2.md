````markdown
# 📘 Day 2 - MySQL Practice Log

This file contains MySQL operations practiced on Day 2, covering table creation, inserting records, default values, constraints like `NOT NULL`, and `AUTO_INCREMENT`.

---

## 🔍 Show Databases

```sql
SHOW DATABASES;
````

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

## 📂 Select Database

```sql
USE mycat;
```

**Output:**

```
Database changed
```

---

## 📋 Show Tables (Empty Initially)

```sql
SHOW TABLES;
```

**Output:**

```
Empty set (0.00 sec)
```

---

## 👥 Create `people` Table

```sql
CREATE TABLE people (
    first_name VARCHAR(20),
    last_name VARCHAR(20),
    age INT
);
```

**Describe Table:**

```sql
DESC people;
```

**Output:**

```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| first_name | varchar(20) | YES  |     | NULL    |       |
| last_name  | varchar(20) | YES  |     | NULL    |       |
| age        | int         | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
```

---

## ➕ Insert & View Records in `people`

```sql
INSERT INTO people (first_name, last_name, age)
VALUES ('A', 'Kumar', 13);
```

```sql
SELECT * FROM people;
```

**Output:**

```
+------------+-----------+------+
| first_name | last_name | age  |
+------------+-----------+------+
| A          | Kumar     |   13 |
+------------+-----------+------+
```

**Insert Multiple Rows:**

```sql
INSERT INTO people (first_name, last_name, age)
VALUES ('B','Rana',24),
       ('C','Jain',21),
       ('D','Maharaj',31);
```

```sql
SELECT * FROM people;
```

**Output:**

```
+------------+-----------+------+
| first_name | last_name | age  |
+------------+-----------+------+
| A          | Kumar     |   13 |
| B          | Rana      |   24 |
| C          | Jain      |   21 |
| D          | Maharaj   |   31 |
+------------+-----------+------+
```

---

## 👶 Create `child` Table with `NOT NULL`

```sql
CREATE TABLE child (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
);
```

**Insert Record:**

```sql
INSERT INTO child (name, age) VALUES ('Ab', 31);
```

**Incorrect Insert (missing age):**

```sql
INSERT INTO child (name) VALUES ('Ab');
-- ERROR 1136: Column count doesn't match value count
```

**Check Data:**

```sql
SELECT * FROM child;
```

**Output:**

```
+------+-----+
| name | age |
+------+-----+
| Ab   |  31 |
+------+-----+
```

---

## 👪 Create `parent` Table with `DEFAULT` Values

```sql
CREATE TABLE parent (
    name VARCHAR(100) DEFAULT 'fname',
    age INT DEFAULT 0
);
```

**Incorrect Insert (missing column):**

```sql
INSERT INTO parent (name, age) VALUES ('AbP');
-- ERROR 1136
```

**Correct Insert using default for `age`:**

```sql
INSERT INTO parent (name) VALUES ('AbP');
```

```sql
SELECT * FROM parent;
```

**Output:**

```
+------+-----+
| name | age |
+------+-----+
| AbP  |   0 |
+------+-----+
```

---

## 🐱 Create `u_cats` Table with `PRIMARY KEY`

```sql
CREATE TABLE u_cats (
    cat_id INT NOT NULL,
    name VARCHAR(100),
    PRIMARY KEY (cat_id)
);
```

**Insert Record:**

```sql
INSERT INTO u_cats (cat_id, name) VALUES (1, 'A');
```

**Duplicate Insert (error):**

```sql
INSERT INTO u_cats (cat_id, name) VALUES (1, 'A');
-- ERROR 1062: Duplicate entry for PRIMARY KEY
```

```sql
SELECT * FROM u_cats;
```

**Output:**

```
+--------+------+
| cat_id | name |
+--------+------+
|      1 | A    |
+--------+------+
```

---

## 🐾 Create `u_cats2` Table with `AUTO_INCREMENT`

**Wrong attempt (spelling mistake):**

```sql
CREATE TABLE u_cats2 (
    cat_id INT NOT NULL AUTO_INCREMENET,
    -- ERROR: syntax error
```

**Correct Version:**

```sql
CREATE TABLE u_cats2 (
    cat_id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(100),
    PRIMARY KEY (cat_id)
);
```

**Insert Records Without ID (auto-generated):**

```sql
INSERT INTO u_cats2 (name) VALUES ('A');
INSERT INTO u_cats2 (name) VALUES ('B');
```

```sql
SELECT * FROM u_cats2;
```

**Output:**

```
+--------+------+
| cat_id | name |
+--------+------+
|      1 | A    |
|      2 | B    |
+--------+------+
```

---

## ✅ Summary of Day 2

| Topic                    | Command/Concept          | Notes                              |
| ------------------------ | ------------------------ | ---------------------------------- |
| Using database           | `USE mycat`              | Switch to specific DB              |
| Creating table           | `CREATE TABLE`           | Structure with types, constraints  |
| Describing table         | `DESC table_name`        | Schema info                        |
| Inserting data           | `INSERT INTO ... VALUES` | Insert single and multiple rows    |
| Constraints              | `NOT NULL`, `DEFAULT`    | Prevent empty and provide defaults |
| Primary Key              | `PRIMARY KEY (col)`      | Ensures uniqueness                 |
| Auto-incrementing fields | `AUTO_INCREMENT`         | Automatically generate unique IDs  |
| Errors encountered       | `ERROR 1136`, `1062`     | Column mismatch, duplicate keys    |

---

🗓️ **End of Day 2 Practice**


