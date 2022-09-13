# mySQL union

<p>a UNION is a sql operator used to combine the results of multiple SELECT statements into one</p>
<p>UNION's have to have the same number of columns AND the same number of DATA TYPES</p>

- [] find a list of employee and branch names
- my answer was incorrect

```
SELECT employee.first_name, employee.last_name, branch.branch_name
FROM employee, branch;
```

- correct answer using UNION operator

```
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch;
```

## this will work in a UNION

```
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch;
```

## this WILL NOT work in a UNION

```
SELECT first_name, last_name
FROM employee
UNION
SELECT branch_name
FROM branch;
```
