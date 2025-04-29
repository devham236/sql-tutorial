## Joins

- Mit 'joins' können wir verschiedene Tabellen anhand einer gemeinsamen Spalte zusammensetzen bzw. kombinieren
- Zum Beispiel wollen wir alle 'branches' und die Namen der Manager herausfinden

```js
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
JOIN branch
ON employee.emp_id = branch.mgr_id;
```

- Mit dem Join statement haben wir Einträge von der employee und branch Tabelle zusammengestzt, wo die emp_id gleich die mgr_id ist.
