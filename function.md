# mySQL functions

- [x] find the number of employees

```
SELECT COUNT(emp_id)
FROM employee;
```

- [x] find the number of employees with a supervisor

```
SELECT COUNT(super_id)
FROM employee;
```

- [] find the number of female employees born after 1970
- my answer was incorrect

```
SELECT COUNT(sex)
FROM employee
WHERE sex = 'F' AND birth_day > 1970-01-01;
```

- correct answer

```
SELECT COUNT(emp_id)
FROM employee
WHERE sex = 'F' AND birth_day > '1970-01-01';
```

- [x] find the average salary of all employees

```
SELECT AVG(salary)
FROM employee;
```

- [x] find the average salary of all male employees

```
SELECT AVG(salary)
FROM employee
WHERE sex = 'M';
```

- [x] find the sum of all employees salaries

```
SELECT SUM(salary)
FROM employee;
```

## AGGREGATION

- [] find out how many males and females there are
- use the GROUP BY clause when using aggregation
- my answer was incorrect

```
SELECT COUNT(SUM(emp_id))
FROM employee
WHERE sex = 'F' AND sex = 'M';
```

- correct answer

```
SELECT COUNT(sex), sex
FROM employee
GROUP BY sex;
```

- [x] find the total sales of each salesman

```
SELECT SUM(total_sales), emp_id
FROM works_with
GROUP BY emp_id;
```

- [x] find out how much money each client spent in the branch

```
SELECT SUM(total_sales), client_id
FROM works_with
GROUP BY client_id;
```
