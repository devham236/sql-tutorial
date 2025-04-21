### Company Database Tables

<img width="639" alt="Bildschirmfoto 2025-04-19 um 15 04 41" src="https://github.com/user-attachments/assets/09c31fb6-31a2-4bdd-a911-88b04a0dff32" />

- Zuerst müssen wir alle Tabellen erstellen und mit Daten füllen.
- Wichtig ist, dass ein paar Tabellen 'Foreign Keys' haben, die sich auf andere Primary Keys beziehen.

### Employee

- Die 'employee' Tabelle hat die 'emp_id' Spalte/Column als 'Primary Key'.
- Die 'super_id' und die 'branch_id' sind 'Foreign Keys'
- 'super_id' bezieht sich auf die 'emp_id', 'branch_id' bezieht sich auf den Primary Key 'branch_id' von der 'branch' Tabelle.
