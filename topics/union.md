## Unions

- Mit Unions können wir mehrere 'SELECT' statements miteinander kombinieren.

```js
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch;
```

- wichtig ist das die Anzahl der Spalten/Columns in beiden SELECT statements übereinstimmt.
