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

- Im Beispiel oben bekommt man eine lange Liste mit all den Einträgen zu 'first_name' und 'branch_name'. Der Spaltenname der Ergebnisse ist aber 'first_name'.

```js
SELECT first_name AS company_names
FROM employee
UNION
SELECT branch_name
FROM branch;
```

- Mit dem 'AS' keyword kann man dem Spaltennamen einen neuen Wert geben.
