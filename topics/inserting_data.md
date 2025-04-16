## Inserting Data

```js
INSERT INTO student VALUES(2, 'Kate', 'Sociology');
```

- Mit 'INSERT INTO' kann man eine Reihe/Row der genannten Tabelle hinzufügen.

```js
INSERT INTO student(student_id, name) VALUES(2, 'Kate');
```

- Wir können auch innerhalb von 'student()' definieren welche Spalten/Columns betroffen sind bzw. welche Spalten/Columns Werte bekommen.
- Die Reihenfolge und Anzahl der betroffenen Spalten/Columns und der neuen Werte müssen dabei immer übereinstimmen.
- Wenn die Tabelle eine Spalte/Column hat, die wir aber nicht im 'INSERT' statement erwähnen (z.B lassen wir 'major' weg), dann ist der Wert dafür standardmäßig null

### Constraints(Einschränkungen)

- Mit 'Not Null' können wir definieren das eine Spalte/Column nicht null als Wert haben darf bzw. immer einen Wert haben muss
  (ähnlich wie bei MongoDB => 'required')

```js
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20) NOT NULL,
    major VARCHAR(20)
);
INSERT INTO student(student_id, major) VALUES(5, 'Computer Science');
```

- Wenn wir dann versuchen nur eine 'student_id' und 'major' hinzuzufügen, bekommen wir einen error: 'Field 'name' doesn't have a default value'

- Mit 'UNIQUE' bestimmen wir das zwei verschiedene Reihen/Rows nicth denselben Wert für eine Spalte/Column haben dürfen, verhindern also Duplikate.

```js
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20) NOT NULL,
    major VARCHAR(20) UNIQUE
);
```

- Mit 'DEFAULT' können wir einen Standard Wert für eine Spalte/Column bestimmen, wenn eine Reihe/Row keinen Wert für diese Spalte/Column definiert hat.

```js
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20),
    major VARCHAR(20) DEFAULT 'undecided'
);
INSERT INTO student(student_id, name) VALUES(1, 'Bob');
```
