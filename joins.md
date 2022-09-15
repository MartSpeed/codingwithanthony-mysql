# mySQL joins

<p>JOIN is used to combine rows from 2 or more tables based on a related column between them into a single result</p>

## adding new branch VALUE

```
INSERT INTO branch VALUES(4, 'Buffalo', NULL, NULL);
```

- [x] find all branches and the names of their managers

```
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
JOIN branch
ON employee.emp_id = branch.mgr_id;
```

- [x] LEFT JOIN, includes all of the rows from the LEFT table (the employee table)
- LEFT JOIN is the table in the FROM clause (employee table)

```
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
LEFT JOIN branch
ON employee.emp_id = branch.mgr_id;
```

- [x] RIGHT JOIN, includes all of the rows from the RIGHT table (the branch table)
- RIGHT JOIN is the table in the JOIN clause (branch table)

```
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
RIGHT JOIN branch
ON employee.emp_id = branch.mgr_id;
```

- the last join is a FULL OUTER JOIN, which displays all of the rows from the left and right tables. mySQL does not support the FULL OUTER JOIN.
