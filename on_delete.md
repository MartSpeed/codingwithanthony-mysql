# mySQL on delete

- deleting entries in the database when they have foreign keys associated with them

1. ON DELETE SET NULL
2. ON DELETE SET CASCADE, if the foreign key gets deleted, then we remove the entire row in the database

## resetting the branch table database

```
CREATE TABLE branch(
branch_id INT PRIMARY KEY,
branch_name VARCHAR(40),
mgr_id INT,
mgr_start_date DATE,
FOREIGN KEY(mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL
);
```

- [x] delete michael scott from the database
- using ON DELETE SET NULL

```
DELETE FROM employee
WHERE emp_id = 102;
```

## resetting the branch_supplier table database

```
CREATE TABLE branch_supplier(
branch_id INT,
supplier_name VARCHAR(40),
supply_type VARCHAR (40),
PRIMARY KEY(branch_id, supplier_name),
FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE CASCADE
);
```

- [x] delete all branch_id with the foreign key of 2 in branch table

```
DELETE FROM branch
WHERE branch_id = 2;
```
