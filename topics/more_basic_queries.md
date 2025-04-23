## More Basic Queries

- Wenn wir eine Liste von der 'employee' Tabelle haben möchten mit all den Vor- und Nachnamen, die Spaltennamen aber anders heißen, 'first_name' und 'last_name', kann man 'AS' verwenden

```js
SELECT first_name AS Vorname, last_name AS Nachname
FROM employee;
```
