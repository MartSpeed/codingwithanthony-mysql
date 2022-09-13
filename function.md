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
- my answer was wrong

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

- [] find the sum of all employees salaries

```
SELECT SUM(salary)
FROM employee;
```
