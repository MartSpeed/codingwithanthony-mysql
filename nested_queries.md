# mySQL nested queries

- a nested query is when we use multiple SELECT statement to get a specific piece of information.

- advanced query writing

- keep practicing the nested queries, find more examples in the mySQL book to use and test

## nested queries

- [] find names of all employees who have sold over $30,000 to a single client

1. query all employees that have sold over 30,000 to a single client
2. get employees first_name & last_name
3. select all employee.emp_id from the works_with.emp_id

- my answer was incorrect

```
SELECT employee.first_name, employee.last_name
FROM employee
JOIN works_with
ON employee.emp_id = works_with.emp_id
WHERE total_sales > 30000;
```

- correct answer

```
SELECT employee.first_name, employee.last_name
FROM employee
WHERE employee.emp_id IN (
	SELECT works_with.emp_id
	FROM works_with
	WHERE works_with.total_sales > 30000
);
```

- [] find all client who are handled by the branch that Michael Scott manages. Assume you know Michael's ID

1. what branch does Michael Scott manage

- incorrect answer

```
SELECT employee.branch_id
FROM employee
WHERE first_name = 'Michael';
```

- correct answer

```
SELECT branch.branch_id
FROM branch
WHERE branch.mgr_id = 102;
```

2. get all of the clients that are handled by that branch

```
SELECT client.client_name
FROM client
WHERE client.branch_id = 2;
```

3. nest the 2nd query with the first query using the next query WHERE clause

```
SELECT client.client_name
FROM client
WHERE client.branch_id = (
	SELECT branch.branch_id
	FROM branch
	WHERE branch.mgr_id = 102
);
```
