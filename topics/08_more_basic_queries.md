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

#### COUNT

- Um herauszufinden wie viele 'employees' in der 'employee' Tabelle sind, kann man die 'COUNT()' methode verwenden

```js
SELECT COUNT(emp_id)
FROM employee;
```

- Wir können mithilfe der 'COUNT()' Methode auch die Abfrage erweitern,
  z.B wenn wir wissen möchten wie viele weibliche employees es gibt, die nach einem bestimmtem Datum geboren wurden.

```js
SELECT COUNT(emp_id)
FROM employee
WHERE employee.sex = 'F' AND employee.birth_date > '1971-01-01';
```

#### AVG

- Mit der methode 'AVG()' findet man den Durchschnitt aller Werte in einer Spalte/Column heraus.

```js
SELECT AVG(salary)
FROM employee;
```

#### SUM

- Mit 'SUM()' kann man die Summer aller Werte in einer Spalte/Column heruasfinden.

```js
SELECT SUM(salary)
FROM employee;
```

- Um darzustellen wie viele Einträge es bei bestimmten Spalten/Columns gibt, z.B wie viele weibliche und männliche 'employees' es in der 'employee' Tabelle gibt, geht man wie folgt vor

```js
SELECT COUNT(sex), sex
FROM employee
GROUP BY sex;
```
