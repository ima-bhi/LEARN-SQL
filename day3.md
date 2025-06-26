
````markdown
# 📘 Day 3 - MySQL Practice Log

## 📋 Show Existing Tables

````sql
SHOW TABLES;
```

**Output:**

```
+-----------------+
| Tables_in_mycat |
+-----------------+
| child           |
| parent          |
| people          |
| u_cats          |
| u_cats2         |
+-----------------+
```

---

## 🐱 Create Table `cats`

```sql
CREATE TABLE cats (
    cat_id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(100),
    breed VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
);
```

**Output:**

```
Query OK, 0 rows affected (0.05 sec)
```

---

## 🧾 Describe `cats` Table

```sql
DESC cats;
```

**Output:**

```
+--------+--------------+------+-----+---------+----------------+
| Field  | Type         | Null | Key | Default | Extra          |
+--------+--------------+------+-----+---------+----------------+
| cat_id | int          | NO   | PRI | NULL    | auto_increment |
| name   | varchar(100) | YES  |     | NULL    |                |
| breed  | varchar(100) | YES  |     | NULL    |                |
| age    | int          | YES  |     | NULL    |                |
+--------+--------------+------+-----+---------+----------------+
```

---

## ➕ Insert Multiple Records

```sql
INSERT INTO cats (name, breed, age)
VALUES 
    ('Ringo', 'Tabby', 4),
    ('Cindy', 'Maine Coon', 10),
    ('Dumbledore', 'Maine Coon', 11),
    ('Egg', 'Persian', 4),
    ('Misty', 'Tabby', 13),
    ('George Michael', 'Ragdoll', 9),
    ('Jackson', 'Sphynx', 7);
```

**Output:**

```
Query OK, 7 rows affected (0.03 sec)
Records: 7  Duplicates: 0  Warnings: 0
```

---

## 📄 View All Data from `cats`

```sql
SELECT * FROM cats;
```

**Output:**

```
+--------+----------------+------------+------+
| cat_id | name           | breed      | age  |
+--------+----------------+------------+------+
|      1 | Ringo          | Tabby      |    4 |
|      2 | Cindy          | Maine Coon |   10 |
|      3 | Dumbledore     | Maine Coon |   11 |
|      4 | Egg            | Persian    |    4 |
|      5 | Misty          | Tabby      |   13 |
|      6 | George Michael | Ragdoll    |    9 |
|      7 | Jackson        | Sphynx     |    7 |
+--------+----------------+------------+------+
```

---

## 🔍 Select Only `name`

```sql
SELECT name FROM cats;
```

**Output:**

```
+----------------+
| name           |
+----------------+
| Ringo          |
| Cindy          |
| Dumbledore     |
| Egg            |
| Misty          |
| George Michael |
| Jackson        |
+----------------+
```

---

## 🔎 Select `name` and `age`

```sql
SELECT name, age FROM cats;
```

**Output:**

```
+----------------+------+
| name           | age  |
+----------------+------+
| Ringo          |    4 |
| Cindy          |   10 |
| Dumbledore     |   11 |
| Egg            |    4 |
| Misty          |   13 |
| George Michael |    9 |
| Jackson        |    7 |
+----------------+------+
```

---

## 🔍 Filter: Cats with Age = 4

```sql
SELECT name, age FROM cats WHERE age = 4;
```

**Output:**

```
+-------+------+
| name  | age  |
+-------+------+
| Ringo |    4 |
| Egg   |    4 |
+-------+------+
```

---

## 🪪 Rename Column in Output using `AS`

```sql
SELECT cat_id AS id, name FROM cats;
```

**Output:**

```
+----+----------------+
| id | name           |
+----+----------------+
|  1 | Ringo          |
|  2 | Cindy          |
|  3 | Dumbledore     |
|  4 | Egg            |
|  5 | Misty          |
|  6 | George Michael |
|  7 | Jackson        |
+----+----------------+
```

---

## ✅ Summary of Day 3

| Task                           | Description                          |
| ------------------------------ | ------------------------------------ |
| `SHOW TABLES`                  | Listed existing tables               |
| `CREATE TABLE` with PK & AI    | Created `cats` with `AUTO_INCREMENT` |
| `INSERT INTO ... VALUES (...)` | Inserted multiple cat records        |
| `SELECT *`                     | Fetched full table                   |
| `SELECT name`                  | Retrieved only names                 |
| `SELECT name, age`             | Retrieved selected columns           |
| `WHERE` Clause                 | Filtered cats by age = 4             |
| `AS` keyword                   | Renamed output columns               |

---

