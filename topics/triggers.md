## Triggers

- Mit trigger functions kannst du definieren was passieren soll wen eine bestimmte Aktion oder ein bestimmter SQL Befehl ausgeführt wird.

```js
DELIMITER $$
CREATE
    TRIGGER my_trigger BEFORE INSERT
    ON employee
    FOR EACH ROW BEGIN
        INSERT INTO trigger_test VALUES('added new employee');
    END $$
DELIMITER;
```

- Hier bestimmen wir etwas das bevor ein neuer Eintrag der employee Tabelle hinzugefügt wird, ausgeführt wird.
- Für jeden Eintrag in der employee Tabelle, wird der trigger_test Tabelle ein string hinzugefügt.

- 'DELIMITER $$' bedeutet man definiert einen neuen Endpunkt, also der Punkt der das Ende eines Befehl beschreibt, sonst war es immer ;
- Nach dem 'FOR EACH' beenden wir dann den trigger und redfinieren den Delimiter als ;
