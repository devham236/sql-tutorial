## Basic Queries (Getting Data)

- Mit 'SELECT' können wir auf die Einträge der definierten Tabelle zugreifen

```js
SELECT * FROM student;
```

- So bekommen wir alle Informationen in der 'student' Tabelle

- Wenn wir aber gezielt nur bestimmte Informationen haben möchten, können wir bestimmte Spalten/Columns bzw. bestimmte Informationen der Einträge.

```js
SELECT student.major FROM student;

//oder major und name

SELECT student.major, student.name FROM student;

```

- Wir können außerdem bestimmen wie die bestimmte Information angezigt werden soll, zum Beispiel alphabetisch nach den Namen:

```js
SELECT student.name, student.major
FROM student
ORDER BY name;

//oder wenn wir alphabetisch aber 'descending' also umgekehrt haben möchten

SELECT student.name, student.major
FROM student
ORDER BY name DESC;
```
