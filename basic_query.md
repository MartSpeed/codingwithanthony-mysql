# basic query for company database

- [x] find all employees

```
SELECT *
FROM employee;
```

- [x] find all clients

```
SELECT *
FROM client;
```

- [x] find all employees ordered by salary

```
SELECT *
FROM employee
ORDER BY salary;
```

- [x] find all employees ordered by sex and then name

```
SELECT *
FROM employee
ORDER BY sex, first_name, last_name;
```

- [x] find the first 5 employees in the able

```
SELECT *
FROM employee
LIMIT 5;
```
