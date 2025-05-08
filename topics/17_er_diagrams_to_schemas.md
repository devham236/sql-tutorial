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
