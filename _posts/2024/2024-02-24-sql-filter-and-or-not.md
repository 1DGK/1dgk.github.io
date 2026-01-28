---
layout: post
title: SQL Filters with AND, OR, and NOT
---
Here are a few examples of how to:
- run SQL queries to retrieve information from a database and
- apply AND, OR, and NOT operators to filter SQL queries.

Find unsuccessful login attempts that happened after 1800:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00:00' AND success = 0;
```

Now check for any failed login attempts that happened on two days:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';
```

Now check for any failed login attempts that happened outside of a country, e.g. Mexico:
```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```
To see the columns and values in the `employees` table:
```sql
SELECT *
FROM employees;
```

Get `employee_id` that work in `Marketing` and work in the East building:
```sql
SELECT *
    -> FROM employees
    -> WHERE department = 'Marketing' AND office LIKE 'East%';
```

Next grab employee id's from Finance and Sales:
```sql
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```

Finally, list everyone who doesn't work in the IT department:
```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```