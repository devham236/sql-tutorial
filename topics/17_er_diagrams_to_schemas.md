## Converting ER Diagrams to Database Schemas

- Wenn wir das ER Diagram fertiggestellt haben, muss dieses nun in ein DB Schema konvertiert werden.

<img width="1235" alt="Bildschirmfoto 2025-05-08 um 10 03 26" src="https://github.com/user-attachments/assets/67320e1e-2c68-4d13-9b32-a460809c182c" />

### 1. Normale Entitäten

- Zuerst erstellen wir für alle 'normalen' Entitäten, also unabhängige Entitäten mit einfachen Attributen, Tabellen in der Database.
- In diesem Fall sind es die **employee**, **client** und **branch** Entitäten.

<img width="898" alt="Bildschirmfoto 2025-05-08 um 10 11 56" src="https://github.com/user-attachments/assets/ae4a7248-d324-421e-8f32-f9e787d06e85" />

```js
CREATE TABLE emloyee (
    emp_id INT PRIMARY KEY,
    first_name VARCHAR(30),
    last_name VARCHAR(30),
    birth_date DATE,
    sex VARCHAR(1),
    salary INT
);

CREATE TABLE client (
    client_id INT PRIMARY KEY,
    client_name VARCHAR(30),
);

CREATE TABLE branch (
    branch_id INT PRIMARY KEY,
    branch_name VARCHAR(30),
);
```

### 2. Schwache Entitäten

- Als nächstes können wir für die schwachen Entitäten, Tabellen erstellen.
- In diesem Fall wäre es die **branch_supplier** Entität.
- Die primary keys von **branch_supplier** bestehen aus **branch_id** und **supplier_name**, ist also ein composit key.

<img width="583" alt="Bildschirmfoto 2025-05-08 um 10 21 54" src="https://github.com/user-attachments/assets/9312ff03-066a-4c8d-9c85-dbae7d6f4c4a" />

```js
CREATE TABLE branch_supplier (
  branch_id INT,
  supplier_name VARCHAR(40),
  supply_type VARCHAR(40),
  PRIMARY KEY(branch_id, supplier_name),
  FOREIGN KEY(branch_id) REFERENCES branch(branch_id) ON DELETE CASCADE
);
```

### 3. Binäre 1:1 Beziehungen

- Jetzt bearbeiten wir die Entitäten die in einer 1:1 Beziehung miteinander stehen.
- In dem wir einen Foreign Key der Tabelle/Entität geben die in totaler Partizipation zur Beziehung mit der anderen Entity steht, also bekommt **branch** einen Foreign Key 'mgr_id' der auf die 'emp_id' von **employee** verweist.

<img width="782" alt="Bildschirmfoto 2025-05-08 um 10 29 49" src="https://github.com/user-attachments/assets/0676c9c4-cf4a-4498-9166-5418fb4320a2" />

```js
ALTER TABLE branch
ADD FOREIGN KEY(mgr_id)
REFERENCES employee(emp_id)
ON DELETE SET NULL;
```

### 4. Binäre 1:N Beziehungen

- Nun schauen wir uns die Entitäten mit einer 1:N Beziehung an.
- In dem wir einen Foreign Key der Entität geben die N zur Beziehung steht, welcher auf einen Primary Key der Entität die 1 zur Beziehung steht verweist.
- In diesem Fall sind es die Branch - Employee (Works for), Employee - Employee (Supervision) und die Client - Branch (Handles) Beziehungen.

<img width="924" alt="Bildschirmfoto 2025-05-08 um 10 39 12" src="https://github.com/user-attachments/assets/fc58e572-bcd1-4f03-a7a0-7b1f9f8a3ed7" />

```js
ALTER TABLE employee
ADD FOREIGN KEY(branch_id)
REFERENCES branch(branch_id)
ON DELETE SET NULL;

ALTER TABLE employee
ADD FOREIGN KEY(super_id)
REFERENCES employee(emp_id)
ON DELETE SET NULL;

ALTER TABLE client
ADD FOREIGN KEY(branch_id)
REFERENCES branch(branch_id)
ON DELETE SET NULL;
```

### 5. Binäre M:N Beziehungen

- Zuletzt schauen wir uns die Entitäten mit einer M:N Beziehung an.
- In dem wir eine neue Tabelle erstellen, wo der Primary Key aus den Primary Keys der beiden Entitäten besteht.
- Hier wären es die Employee und Client Tabellen/Entitäten.

<img width="737" alt="Bildschirmfoto 2025-05-08 um 10 45 53" src="https://github.com/user-attachments/assets/c8d19a42-660f-402c-aa11-b34c9cac21a8" />

```js
CREATE TABLE works_on (
  emp_id INT,
  client_id INT,
  total_sales INT,
  PRIMARY KEY(emp_id, client_id),
  FOREIGN KEY(emp_id) REFERENCES employee(emp_id) ON DELETE CASCADE,
  FOREIGN KEY(client_id) REFERENCES client(client_id) ON DELETE CASCADE
);
```
