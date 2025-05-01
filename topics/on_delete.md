## On Delete

### Set Null

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

- Im CREATE statement, definieren wir einen Foreign Key 'mgr_id' der auf die 'emp_id' von der employee Tabelle verweist, wenn dieser Foreign Key gelöscht wird bzw. wenn die 'emp_id' gelöscht wird, bekommt die 'mgr_id' automatisch null als Wert.

### Cascade

- Wenn man die ganze Zeile bzw. den EIntrag löschen möchte wenn der verweiste Key gelöscht wird, kann man ON DELETE CASCADE verwenden.

```js
CREATE TABLE branch_supplier (
    branch_id INT,
    supplier_name VARCHAR(40),
    supplier_type VARCHAR(40),
    PRIMARY KEY(branch_id, supplier_name)
    FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE CASCADE
);
```
