---
layout: post
title: How to Filter a SQL Query
---
This activity is pulled from the fourth course in the Google Cybersecurity Certificate. [See my notes here](https://1dgk.github.io/2024/02/16/gcc-course-4.html).
---

In this scenario we'll apply basic filters to SQL queries to retrieve information from a database.

First list all organization machines (`device_id`) and their operating systems (`operating_system`). The data is contained in a table called `machines`:
```sql
SELECT device_id, operating_system FROM machines;
```
This returns a list of 200 rows. Let's go further. There are three types of operating systems installed on the various devices. To list all devices that have the second type of operating system (`OS 2`) installed:
```sql
SELECT device_id, operating_system
FROM machines
WHERE operating_system = 'OS 2';
```
This narrows the list down to 80 machines that have `OS 2` installed.

Next, list all employees in the fictional finance and sales department:
```sql
SELECT *
FROM employees
WHERE department = 'Finance';
```

There's an issue with a machine in the fictional building of `South-109`. Let's find which employee uses that machine:
```sql
SELECT *
FROM employees
WHERE office = 'South-109';
```

Let's say every machine in building `South` has an issue. To list all devices in that building:
```sql
SELECT *
FROM employees
WHERE office LIKE 'South%'
```