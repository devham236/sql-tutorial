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
