# SQL Queries for Data Extraction

## Data Analytics Internship – Task 7

### Submitted By

**Arshpreet Singh**

## Project Overview

This project demonstrates fundamental and intermediate SQL concepts used for data extraction and analysis in relational databases. The implementation includes database creation, table management, data insertion, filtering, joining tables, aggregation functions, grouping, subqueries, and sorting operations.

The project was developed as part of the **Data Analytics Internship Task 7** to strengthen database querying and data retrieval skills using SQL.

---

## Technologies Used

* MySQL
* SQL
* Relational Database Management System (RDBMS)
* GitHub

---

## Database Structure

### Students Table

| Column Name  | Data Type   |
| ------------ | ----------- |
| student_id   | INT         |
| student_name | VARCHAR(50) |
| major        | VARCHAR(10) |

### Enrollments Table

| Column Name   | Data Type   |
| ------------- | ----------- |
| enrollment_id | INT         |
| student_id    | INT         |
| course_name   | VARCHAR(50) |
| fee           | INT         |

---

## Features Implemented

### 1. Database Creation

```sql
CREATE DATABASE internship_sql;
USE internship_sql;
```

### 2. Table Creation

* Students Table
* Enrollments Table

### 3. Data Insertion

Sample student and enrollment records were inserted into the database for query execution and testing.

### 4. Data Retrieval

Retrieve all student records:

```sql
SELECT * FROM students;
```

### 5. Data Filtering

Retrieve students from the CSE department:

```sql
SELECT student_name
FROM students
WHERE major='CSE';
```

### 6. INNER JOIN

Display students along with their enrolled courses:

```sql
SELECT s.student_name, e.course_name
FROM students s
INNER JOIN enrollments e
ON s.student_id=e.student_id;
```

### 7. LEFT JOIN

Display all students including those without enrollments:

```sql
SELECT s.student_name, e.course_name
FROM students s
LEFT JOIN enrollments e
ON s.student_id=e.student_id;
```

### 8. GROUP BY and COUNT

Count students in each major:

```sql
SELECT major,
COUNT(*) AS total_students
FROM students
GROUP BY major;
```

### 9. Aggregate Functions

#### SUM

```sql
SELECT SUM(fee) AS total_fee
FROM enrollments;
```

#### AVG

```sql
SELECT AVG(fee) AS average_fee
FROM enrollments;
```

### 10. HAVING Clause

Display departments having more than one student:

```sql
SELECT major,
COUNT(*) AS total_students
FROM students
GROUP BY major
HAVING COUNT(*) > 1;
```

### 11. Subquery

Display courses having fees greater than the average fee:

```sql
SELECT course_name, fee
FROM enrollments
WHERE fee >
(
SELECT AVG(fee)
FROM enrollments
);
```

### 12. ORDER BY

Sort enrollments based on fee in descending order:

```sql
SELECT *
FROM enrollments
ORDER BY fee DESC;
```

---

## Learning Outcomes

* Understanding relational databases
* Creating and managing tables
* Writing SQL queries
* Data filtering using WHERE clause
* Combining tables using JOIN operations
* Performing aggregations using SQL functions
* Using GROUP BY and HAVING clauses
* Implementing subqueries
* Sorting and organizing query results

---

## Interview Questions

### What is the difference between INNER JOIN and LEFT JOIN?

**INNER JOIN**

* Returns only matching records from both tables.
* Excludes unmatched rows.

**LEFT JOIN**

* Returns all records from the left table.
* Returns matching records from the right table.
* Unmatched rows contain NULL values.

### What is a Subquery?

A subquery is a query nested inside another SQL query. It is used to perform intermediate calculations, filtering, and advanced data retrieval operations.

Example:

```sql
SELECT course_name, fee
FROM enrollments
WHERE fee >
(
SELECT AVG(fee)
FROM enrollments
);
```

---

## Project Structure

```text
SCREENSHOTS
Data_Analytics_SQL_Queries_Report.docx
SQL_QUERY_FOR_DATAEXTRACTION.sql
README.md
```

---

## Conclusion

This project successfully demonstrates SQL data extraction techniques using relational databases. By implementing SELECT, WHERE, JOIN, GROUP BY, HAVING, aggregate functions, subqueries, and ORDER BY clauses, the project provides practical experience in database querying and analytical data retrieval.

The task helped develop essential SQL skills required for Data Analytics, Business Intelligence, and Database Management roles.
