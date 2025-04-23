## More Basic Queries

### AS

- Wenn wir eine Liste von der 'employee' Tabelle haben möchten mit all den Vor- und Nachnamen, die Spaltennamen aber anders heißen, 'first_name' und 'last_name', kann man 'AS' verwenden

```js
SELECT first_name AS Vorname, last_name AS Nachname
FROM employee;
```

### DISTINCT

- Wenn wir heruasfinden möchten wie viele verschiedene Geschlechter, in unserer 'employee' Tabelle vorhanden sind, kann man 'DISTINCT' verwenden

```js
SELECT DISTINCT sex
FROM employee;
```

### SQL Functions

- Um herauszufinden wie viele 'employees' in der 'employee' Tabelle sind, kann man die 'count()' methode verwenden

```js
SELECT COUNT(emp_id)
FROM employee;
```
