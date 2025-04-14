## SQL Basics

- SQL(Structured Query Language) ist eine "hybride" Sprache um mit RDBMS zu interagieren.
- Können damit die Struktur(Schema) der DB konfigurieren
- C.R.U.D Operationen ausführen
- Tabellen designen und erstellen
- Nicht alle RDBMS implementieren SQL genau gleich

- Es ist eine "hybride" Sprache weil sie aus 4 Typen einer Sprache besteht:

1. Data Query Language (DQL)
2. Data Definition Language (DQL)
3. Data Control Language (DQL)
4. Data Manipulation Language (DQL)

### Queries

- Queries sind Befehle (in SQL geschrieben) die man dem RDBMS geben kann um gewisse Daten zu bekommen.

```js
SELECT employee.name, employee.age
FROM employee
WHERE employee.salary > 30000;
```

### Setup

- Du musst dich erst mit dem SQL Server auf deinem Gerät verbinden bzw. dich anmelden

```bash
mysql -u root -p
```

- Dann das Password eingeben

### Data Types

```js
INT; // Ganze Zahlen
DECIMAL(10, 4); // Dezimalzahlen(Total Digits, Digits after decimal)
VARCHAR(1); // String of text length 1
BLOB; // Binary Large Object
DATE; // 'YYYY-MM-DD'
TIMESTAMP; // 'YYYY-MM-DD HH:MM:SS'
```

### Creating Tables

<img width="352" alt="Bildschirmfoto 2025-04-14 um 09 14 45" src="https://github.com/user-attachments/assets/83ac4f11-2d98-42c4-976f-f1188d0668c5" />

- SQL sollte man (muss man aber nicht) immer uppercased schreiben um die "reserved keywoards" sofort zu erkennen bzw. um den SQL code von den eigenen Texten unterscheiden zu können.
- Außerdem muss nach jedem SQL-Befehl ein Semikolon

```js
CREATE TABLE student (
    student_id INT PRIMARY KEY,
    name VARCHAR(20),
    major VARCHAR(20)
);

// Primary Keys kannst du auch so definieren

CREATE TABLE student (
    student_id INT,
    name VARCHAR(20),
    major VARCHAR(20),
    PRIMARY KEY(student_id)
);
```

- Mit 'CREATE TABLE' können wir unsere Tabelle erstellen und im Funktionskörper die einzelnen Spalten/Columns definieren

```js
DESCRIBE student;
```

- Mit 'DESCRIBE table_name' kann man die erstellte Tabelle aufrufen

### Deleting Tables

```js
DROP TABLE table_name;
```

- Mit 'DROP TABLE' können wir Tabelle löschen

### Add/Remove to/from Tables

```js
ALTER TABLE student ADD gpa DECIMAL;
```

- Mit 'ALTER TABLE' und 'ADD' kann man der Tabelle eine neue Spalte/Column hinzufügen

```js
ALTER TABLE student DROP COLUMN gpa;
```

- Mit 'ALTER TABLE' und 'DROP COLUMN' kann man der Tabelle eine Spalte/Column entfernen.
