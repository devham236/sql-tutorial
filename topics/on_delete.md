## On Delete

- Was passiert wenn man einen Einträg entfernt der in anderen Tabellen, bzw. wo eine Spalte/Column oder ein Key in einer anderen Tabelle als Foreign Key verwendet wird.

```js
CREATE TABLE branch (
    branch_id INT PRIMARY KEY,
    branch_name VARCHAR(40),
    mgr_id INT,
    mgr_start_date DATE,
    FOREIGN KEY(mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL
);
```
