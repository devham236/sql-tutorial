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
