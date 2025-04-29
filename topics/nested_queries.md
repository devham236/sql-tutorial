## Nested Queries

- Mit nested queries können wir ganz spezifische Informationen erhalten.
- Mit mehreren SLECT statements die voneinader abhäning sind, bzw wo das Ergebnis eines SELECT staements benötigt wird um ein weiteres SELECT statement auszufühern, können wir unsere Tabellen durchsuchen und die gewünschte Information bekommen.
- Zum Beispiel, wenn wir "alle employees finden wollen die mehr als 30.000$ an einen client verkauft haben"

```js
// Zuerst holen wir uns alle emp_id's von der works_with Tabelle wo der total_sales Wert über 30000 liegt

SELECT works_with.emp_id
FROM works_with
WHERE works_with.total_sales > 30000;
```

```js
// Wir wissen das wir die Vor- und Nachnamen von der employee bekommen möchten

SELECT employee.first_name, employee.last_name
FROM employee
WHERE employee.emp_id IN (
    SELECT works_with.emp_id
    FROM works_with
    WHERE works_with.total_sales > 30000
);
```

- So bekommen wir alle Vor- und Nachnamen aller employees, dessen id Teil des Ergebnis des nested SELECT statements ist.

```js
// Finde alle client names die von Michael Scott gemanaged werden.

SELECT client.client_name
FROM client
WHERE client.branch_id = (
    SELECT branch.branch_id
    FROM branch
    WHERE branch.mgr_id = 102
);
```

- Man kann auch das = verwenden in nested queries verwenden
