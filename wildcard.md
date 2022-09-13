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
