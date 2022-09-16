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
