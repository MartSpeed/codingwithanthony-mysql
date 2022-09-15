# mySQL on delete

- deleting entries in the database when they have foreign keys associated with them

1. ON DELETE SET NULL
2. ON DELETE SET NULL

## resetting the database

```
CREATE TABLE branch(
branch_id INT PRIMARY KEY,
branch_name VARCHAR(40),
mgr_id INT,
mgr_start_date DATE,
FOREIGN KEY(mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL
);
```

- [] delete michael scott from the database

```
DELETE FROM employee
WHERE emp_id = 102;
```
