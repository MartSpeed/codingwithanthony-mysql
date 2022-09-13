# mySQL basic query for company database

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

- [x] find the first and last name of all employees

```
SELECT first_name, last_name
FROM employee;
```

- [x] find the forename and surnames of all employees
- used the keyword AS to name the alias tables

```
SELECT first_name AS forename, last_name AS surname
FROM employee;
```

- [x] find out all of the different genders
- DISTINCT keyword used; what are the particular values that are stored in a specific column

```
SELECT DISTINCT sex
FROM employee;
```
