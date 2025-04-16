## Update & Delete

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
