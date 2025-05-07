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

```js
CREATE TABLE works_with(
    emp_id INT,
    client_id INT,
    total_sales INT,
    PRIMARY KEY(emp_id, client_id),
    FOREIGN KEY(emp_id) REFERENCES employee(emp_id) ON DELETE CASCADE,
    FOREIGN KEY(client_id) REFERENCES client(client_id) ON DELETE CASCADE
);
```

### Branch Supplier

<img width="305" alt="Bildschirmfoto 2025-04-21 um 11 55 50" src="https://github.com/user-attachments/assets/dd38734f-d37c-48c0-96bd-acfe2a702d10" />

- Die branch_supplier Tabelle hat einen 'branch_id' Foreign Key.
- Die Primary Keys sind 'supplier_name' und 'branch_id'

```js
CREATE TABLE branch_supplier(
    branch_id INT,
    supplier_name VARCHAR(40),
    supply_type VARCHAR(40),
    PRIMARY KEY(branch_id, supplier_name),
    FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE CASCADE
);
```

### Insert Data into Tables

#### Branch & Employee

```js
-- Corporate
INSERT INTO employee VALUES(100, 'David', 'Wallace', '1967-11-17', 'M', 250000, NULL, NULL);

INSERT INTO branch VALUES(1, 'Corporate', 100, '2006-02-09');

UPDATE employee
SET branch_id = 1
WHERE emp_id = 100;

INSERT INTO employee VALUES(101, 'Jan', 'Levinson', '1961-05-11', 'F', 110000, 100, 1);

-- Scranton
INSERT INTO employee VALUES(102, 'Michael', 'Scott', '1964-03-15', 'M', 75000, 100, NULL);

INSERT INTO branch VALUES(2, 'Scranton', 102, '1992-04-06');

UPDATE employee
SET branch_id = 2
WHERE emp_id = 102;

INSERT INTO employee VALUES(103, 'Angela', 'Martin', '1971-06-25', 'F', 63000, 102, 2);
INSERT INTO employee VALUES(104, 'Kelly', 'Kapoor', '1980-02-05', 'F', 55000, 102, 2);
INSERT INTO employee VALUES(105, 'Stanley', 'Hudson', '1958-02-19', 'M', 69000, 102, 2);

-- Stamford
INSERT INTO employee VALUES(106, 'Josh', 'Porter', '1969-09-05', 'M', 78000, 100, NULL);

INSERT INTO branch VALUES(3, 'Stamford', 106, '1998-02-13');

UPDATE employee
SET branch_id = 3
WHERE emp_id = 106;

INSERT INTO employee VALUES(107, 'Andy', 'Bernard', '1973-07-22', 'M', 65000, 106, 3);
INSERT INTO employee VALUES(108, 'Jim', 'Halpert', '1978-10-01', 'M', 71000, 106, 3);
```

#### Branch Supplier

```js
INSERT INTO branch_supplier VALUES(2, 'Hammer Mill', 'Paper');
INSERT INTO branch_supplier VALUES(2, 'Uni-ball', 'Writing Utensils');
INSERT INTO branch_supplier VALUES(3, 'Patriot Paper', 'Paper');
INSERT INTO branch_supplier VALUES(2, 'J.T. Forms & Labels', 'Custom Forms');
INSERT INTO branch_supplier VALUES(3, 'Uni-ball', 'Writing Utensils');
INSERT INTO branch_supplier VALUES(3, 'Hammer Mill', 'Paper');
INSERT INTO branch_supplier VALUES(3, 'Stamford Lables', 'Custom Forms');
```

#### Client

```js
INSERT INTO client VALUES(400, 'Dunmore Highschool', 2);
INSERT INTO client VALUES(401, 'Lackawana Country', 2);
INSERT INTO client VALUES(402, 'FedEx', 3);
INSERT INTO client VALUES(403, 'John Daly Law, LLC', 3);
INSERT INTO client VALUES(404, 'Scranton Whitepages', 2);
INSERT INTO client VALUES(405, 'Times Newspaper', 3);
INSERT INTO client VALUES(406, 'FedEx', 2);
```

#### Works With

```js
INSERT INTO works_with VALUES(105, 400, 55000);
INSERT INTO works_with VALUES(102, 401, 267000);
INSERT INTO works_with VALUES(108, 402, 22500);
INSERT INTO works_with VALUES(107, 403, 5000);
INSERT INTO works_with VALUES(108, 403, 12000);
INSERT INTO works_with VALUES(105, 404, 33000);
INSERT INTO works_with VALUES(107, 405, 26000);
INSERT INTO works_with VALUES(102, 406, 15000);
INSERT INTO works_with VALUES(105, 406, 130000);
```
