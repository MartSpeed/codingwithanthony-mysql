# mySQL triggers

- triggers is a block of sql code which with define an action that should happen when an operation is performed on the database

1. trigger_test can not have the same name, if trigger_test exist then you need to create a trigger_test1 or trigger_test_name_added

```
CREATE TABLE trigger_test(
	message VARCHAR(100)
);
```

## trigger test example

- before something is inserted into the employee table, enter into the trigger test table the values added 'new employee'

```
DELIMITER $$
CREATE
	TRIGGER my_trigger BEFORE INSERT
    ON employee
    FOR EACH ROW BEGIN
		INSERT INTO trigger_test VALUES('added new employee');
	END$$
DELIMITER ;
```

## adding a new employee trigger_test

```
INSERT INTO employee
VALUES(109, 'Oscar', 'Martinez', '1968-02-19', 'M', 69000, 106, 3);
```

### checking the trigger_test works

```
SELECT *
FROM trigger_test;
```

- [x] result output is 'added new employee'

## trigger test for accessing an attribute about what we inserted

- [] this will return the employee name that was just inserted

```
DELIMITER $$
CREATE
	TRIGGER my_trigger1 BEFORE INSERT
    ON employee
    FOR EACH ROW BEGIN
		INSERT INTO trigger_test VALUES(NEW.first_name);
	END$$
DELIMITER ;
```

### new employee being inserted for trigger_test

```
INSERT INTO employee
VALUES(110, 'Kevin', 'Malone', '1978-02-19', '', 69000, 106, 3);
```

### checking trigger_test1 work

```
SELECT *
FROM trigger_test;
```
