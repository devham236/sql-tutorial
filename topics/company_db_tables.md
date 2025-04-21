### Company Database Tables

<img width="639" alt="Bildschirmfoto 2025-04-19 um 15 04 41" src="https://github.com/user-attachments/assets/09c31fb6-31a2-4bdd-a911-88b04a0dff32" />

- Zuerst müssen wir alle Tabellen erstellen und mit Daten füllen.
- Wichtig ist, dass ein paar Tabellen 'Foreign Keys' haben, die sich auf andere Primary Keys beziehen.

### Employee

<img width="639" alt="Bildschirmfoto 2025-04-21 um 10 45 59" src="https://github.com/user-attachments/assets/901acd96-4d6b-4055-b21a-decfe0811436" />

- Die 'employee' Tabelle hat die 'emp_id' Spalte/Column als 'Primary Key'.
- Die 'super_id' und die 'branch_id' sind 'Foreign Keys'
- 'super_id' bezieht sich auf die 'emp_id', 'branch_id' bezieht sich auf den Primary Key 'branch_id' von der 'branch' Tabelle.

```js
CREATE TABLE employee(
    emp_id INT PRIMARY KEY,
    first_name VARCHAR(40),
    last_name VARCHAR(40),
    birth_date DATE,
    sex VARCHAR(1),
    salary INT,
    super_id INT,
    branch_id INT
);
```

```js
ALTER TABLE employee
ADD FOREIGN KEY(super_id)
REFERENCES employee(emp_id)
ON DELETE SET NULL;
```

- Die 'super_id' bezieht sich auf die 'emp_id' und die 'branch_id' bleibt erstmal ein normaler INT.

### Branch

<img width="330" alt="Bildschirmfoto 2025-04-21 um 10 54 51" src="https://github.com/user-attachments/assets/457f26f4-9b8a-4567-bbcc-833661a62aef" />

- Die 'branch' Tabelle hat die 'branch_id' als Primary Key und die 'mgr_id' als Foreign Key.
- 'mgr_id' bezieht sich auf die 'emp_id' von der employee Tabelle.

```js
CREATE TABLE branch(
    branch_id INT PRIMARY KEY,
    branch_name VARCHAR(20),
    mgr_id INT,
    mgr_start_date DATE,
    FOREIGN KEY(mgr_id) REFERENCES employee(emp_id) ON DELETE SET NULL
);
```

- Um einen Foreign Key zu erstellen, übergibt man die gewünschte Spalte/Column 'FOREIGN KEY(spaltenname)' und die Spalte/Column die referenziert werden soll 'REFERENCES tabellenname(spaltenname)
- 'ON DELETE SET NULL' bedeutet wenn die bezogene Spalte/Column bzw. der Wert (emp_id) gelöscht wird, dann soll der Wert (mgr_id) auf null gesetzt werden.

```js
ALTER TABLE employee
ADD FOREIGN KEY(branch_id)
REFERENCES branch(branch_id)
ON DELETE SET NULL;
```

- Jetzt können wir den Foreign Key 'branch_id' in der employee Tabelle erstellen

### Client

<img width="291" alt="Bildschirmfoto 2025-04-21 um 11 40 40" src="https://github.com/user-attachments/assets/25f2221b-8942-481e-93d0-7effd1c6449c" />

- Die client Tabelle hat die 'client_id' als Primary Key und einen 'branch_id' Foreign Key der auf die 'branch_id' von der branch Tabelle verweist.

```js
CREATE TABLE client(
    client_id INT PRIMARY KEY,
    client_name VARCHAR(40),
    branch_id INT,
    FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE SET NULL
);
```

### Works With

<img width="213" alt="Bildschirmfoto 2025-04-21 um 11 48 25" src="https://github.com/user-attachments/assets/29cc733e-9438-4ffc-b078-62beed624a2c" />

- Die works_with Tabelle hat einen Composit Key, bestehend aus zwei Foreign Key, emp_id von der employee Tabelle und client_id von der client Tabelle.

### Branch Supplier
