---
layout: post
title: Using Operators in SQL Queries
---
SQL queries can be filtered further with:
- the WHERE keyword
- the BETWEEN and AND operators, and
- operators for working with numeric or date and time data types (for example, =, >, >=)

Retrieve data for login attempts made after 2022-05-09:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date > '2022-05-09';
```
In this case, 125 attempts were made after that date.

Now, include 2022-05-09 in the query:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date >= '2022-05-09';
```
That brings the number up to 165 attempts.

Now query attempts between dates:
```sql
SELECT *
FROM log_in_attempts
WHERE login_date
BETWEEN '2022-05-09' AND '2022-05-11';
```
This returns a value of 123 attempts.

Next, check for login attempts at certain times. In this case, before 0700:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time < '07:00:00';
```
Now check login attempts between 0600 and 0700:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time
BETWEEN '06:00:00' AND '07:00:00';
```

Query for login attempts with `event_id` greater than or equal to `100`:
```sql
SELECT *
FROM log_in_attempts
WHERE event_id >= 100;
``` 

Narrow it down to return only login attempts with `event_id` between `100` and `150`:
```sql
SELECT *
FROM log_in_attempts
WHERE event_id
BETWEEN 100 AND 150;
```