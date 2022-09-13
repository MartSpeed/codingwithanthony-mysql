# mySQL union

<p>a UNION is a sql operator used to combine the results of multiple SELECT statements into one</p>
<p>UNION's have to have the same number of columns AND the same number and type of DATA TYPES</p>

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

## you can use more then one UNION is a statement

```
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch
UNION
SELECT client_name
FROM client;
```

- [] find a list of all clients & branch suppliers name

```
SELECT client_name
FROM client
UNION
SELECT supplier_name
FROM branch_supplier;
```

- find a list of all clients & branch suppliers names and id's

```
SELECT client_name, client.branch_id
FROM client
UNION
SELECT supplier_name, branch_supplier.branch_id
FROM branch_supplier;
```
