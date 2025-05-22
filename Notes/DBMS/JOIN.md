```sql
SELECT columns from table1 JOIN_TYPE table2 ON table1.column = table2.column;
```
## Inner Join
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

