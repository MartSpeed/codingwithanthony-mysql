# mySQL triggers

- triggers is a block of sql code which with define an action that should happen when an operation is performed on the database

```
CREATE TABLE trigger_test(
	message VARCHAR(100)
);
```

## trigger test example

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
