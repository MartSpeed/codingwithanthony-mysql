# mySQL wildcard

<p>wild cards are are a way of defining different patterns that we match specific pieces of data to. grab data that matches a specific pattern.</p>

## LIKE keyword

- % = any number of character
- \_ = one character

- [x] find any clients who are an LLC

```
SELECT *
FROM client
WHERE client_name LIKE '%LLC';
```

- [] find any branch suppliers who are in the label business
- my answer was incorrect

```
SELECT *
FROM branch_supplier
WHERE supplier_name LIKE '%label';
```

- correct answer

```
SELECT *
FROM branch_supplier
WHERE supplier_name LIKE '%label%';
```

## UPDATE keyword for the supplier name

```
UPDATE branch_supplier
SET supplier_name = 'Stamford Labels'
WHERE supplier_name = 'Stamford Lables';
```

- [x] find any employee born in october
- this query is correct

```
SELECT *
FROM employee
WHERE birth_day LIKE '%10%';
```

## find any employer born in october

- this query is more correct

```
SELECT *
FROM employee
WHERE birth_day LIKE '%____-10%';
```

- [] find any clients who are schools

```
SELECT *
FROM client
WHERE client_name LIKE '%school';
```
