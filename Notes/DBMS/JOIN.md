```sql
SELECT columns from table1 JOIN_TYPE table2 ON table1.column = table2.column;
```
## Inner Join/ JOIN
An **INNER JOIN** is a type of SQL join that **returns only the rows that have matching values** in both tables.

### ✅ **Syntax**:

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.common_column = table2.common_column;
```

---

### 📘 **Example**:

#### Tables:

**Students**

|student_id|name|
|---|---|
|1|Alice|
|2|Bob|
|3|Charlie|

**Marks**

|student_id|subject|marks|
|---|---|---|
|1|Math|90|
|2|Science|85|
|4|Math|75|

#### Query:

```sql
SELECT Students.name, Marks.subject, Marks.marks
FROM Students
INNER JOIN Marks
ON Students.student_id = Marks.student_id;
```

#### Result:

|name|subject|marks|
|---|---|---|
|Alice|Math|90|
|Bob|Science|85|

➡️ Student ID 3 (Charlie) and ID 4 (in Marks) are **excluded** because there is **no match** in both tables.

---

### 🧠 Summary:

- **INNER JOIN = Only matched rows**
    
- Rows with **no match in either table are excluded**
    
- It's the **most common** type of join


## 🧲 2. **LEFT JOIN** (or **LEFT OUTER JOIN**)

### ✅ Returns: All rows from the **left table**, and matched rows from the **right table**. If no match, `NULL` is shown.

### 📘 Syntax:

```sql
SELECT *
FROM table1
LEFT JOIN table2
ON table1.id = table2.id;
```

### 🔍 Output:

|name|dept|
|---|---|
|Alice|HR|
|Bob|Sales|
|Carol|NULL|

📝 **Note**: All rows from `Employees` are shown. Carol has no department, so `NULL`.

---

## 🧲 3. **RIGHT JOIN** (or **RIGHT OUTER JOIN**)

### ✅ Returns: All rows from the **right table**, and matched rows from the **left table**.

### 📘 Syntax:

```sql
SELECT *
FROM table1
RIGHT JOIN table2
ON table1.id = table2.id;
```

### 🔍 Output:

|name|dept|
|---|---|
|Alice|HR|
|Bob|Sales|
|NULL|Finance|

📝 **Note**: All rows from `Departments` are shown. No matching employee for emp_id 4.

---

## 🧩 4. **FULL JOIN** (or **FULL OUTER JOIN**)

### ✅ Returns: All rows when there is a match in **either** left or right table. Fills `NULL` where there is no match.

### 📘 Syntax:

```sql
SELECT *
FROM table1
FULL JOIN table2
ON table1.id = table2.id;
```

### 🔍 Output:

|name|dept|
|---|---|
|Alice|HR|
|Bob|Sales|
|Carol|NULL|
|NULL|Finance|

📝 **Note**: Combines results of LEFT and RIGHT JOIN.

---

## 🧠 Summary Table

|Join Type|Rows Returned|
|---|---|
|INNER JOIN|Only matching rows in both tables|
|LEFT JOIN|All left + matching right rows (NULL if no match)|
|RIGHT JOIN|All right + matching left rows (NULL if no match)|
|FULL JOIN|All rows from both sides, matched or not|
