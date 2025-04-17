## Update & Delete

### Update

- Um Werte zu bearbeiten könnnen wir wie folgt vorgehen:

```js
UPDATE student
SET major = 'Bio'
WHERE major = 'Biology';
```

- Alle Reihen/Rows die 'Biology' als Wert für die Spalte/Column 'major' wurden angepasst, so dass jetzt 'Bio' der Wert ist

- Die Bedingung kann man auch erweitern:

```js
UPDATE student
SET major = 'Biochemistry'
WHERE major = 'Bio' OR major = 'Chemistry';
```

- Die Aktion, bzw. die Logik die angewendet werden soll, kann auch erweitert werden:

```js
UPDATE student
SET name = 'Tom', major = 'undecided'
WHERE student_id = 3;
```

### Delete

- Um bestimmte Werte zu löschen geht man wie folgt vor:

```js
DELETE FROM student
WHERE student_id = 5;
```

- Alle Reihen/Rows in der 'student' Tabelle mit der 'student_id' 5 werden gelöscht.

- Genau wie bei UPDATE kann die Bedingung erweitert werden.

```js
DELETE FROM student
WHERE name = 'Bob' AND student_id = 1;
```
