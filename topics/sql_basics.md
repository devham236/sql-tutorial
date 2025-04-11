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
