# mySQL converting Entity Relationship diagrams to database schemas

## STEP 1: mapping of regular entity types

- for each regular entity type create a relation (table) thats includes all of the simple attributes of that entity

## create employee entity

```
CREATE TABLE employee(
  emp_id INT PRIMARY KEY,
  first_name VARCHAR(40),
  last_name VARCHAR(40),
  birth_date DATE,
  sex VARCHAR(1),
  salary INT
);
```

## create client entity

```
CREATE TABLE client(
  client_id INT PRIMARY KEY,
  client_name VARCHAR(40)
);
```

## create branch entity

```
CREATE TABLE branch(
  branch_id INT PRIMARY KEY,
  branch_name VARCHAR(40),
);
```

## STEP 2: mapping of weak entity types

- for each weak entity type create a relation (table) that includes all simple attributes of the weak entity
- the primary key of the new relation should be the partial key of the weak entity plus the primary ket of its owner

```
CREATE TABLE branch_supplier(
  supplier_name VARCHAR(40) PRIMARY KEY,
  supply_type VARCHAR(40),
  FOREIGN KEY(branch_id) REFERENCES branch.branch_id
);
```

## STEP 3: mapping of binary 1:! relationship types

- include one side of the relationship as a foreign key in the other favor total participation

```
CREATE TABLE branch(
  branch_id INT PRIMARY KEY,
  branch_name VARCHAR(40),
  mgr_start_date DATE,
  FOREIGN KEY(mgr_id) REFERENCES employee.emp_id
);
```

## STEP 4: mapping of binary 1:N relationship types

- include the 1 side's primary key as a foreign key on the N side relation (table)

```
CREATE TABLE employee(
  emp_id INT PRIMARY KEY,
  first_name VARCHAR(40),
  last_name VARCHAR(40),
  birth_date DATE,
  sex VARCHAR(1),
  salary INT,
  FOREIGN KEY(super_id) REFERENCES emp_id
  FOREIGN KEY(branch_id) REFERENCES branch.branch_id
);

CREATE TABLE client(
  client_id INT PRIMARY KEY
  client_name VARCHAR(40),
  FOREIGN KEY(client.branch_id) REFERENCES branch.branch_id
);
```
