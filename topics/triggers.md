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
