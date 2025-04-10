## Tables and Keys

- Eine Tabelle besteht aus Spalten (columns) und Reihen (rows)
- Eine Spalte beschreibt die ein einzelnes Attribut bzw. eine einzelne property.
- Eine Reihe (rows) beschreibt einen gesamten Eintrag in der DB
  <img width="680" alt="Bildschirmfoto 2025-04-10 um 10 29 23" src="https://github.com/user-attachments/assets/38e396c7-f383-4cf6-88ce-36c3fa850d73" />

- Wenn man eine Tabelle erstellen möchte sollte jede Reihe einen einzigartigen Wert besitzen um sich immer von allen zu unterscheiden.
- Deswegen sollt es immer eine Id Spalte geben.
- Dieser einzigartige Wert wird auch als "Primary Key" bezeichnet.

### Natural Key

- Primary Keys können einen Bezug auf reale Eigenschaften haben, z.B in einer User Tabelle wird die Email Adresse als Primary Key verwendet oder die IBAN eines Benutzers in einer Kunden Tabelle für eine Bank, hier werden diese Keys als "Natural Keys" bezeichnet

### Surrogate(Ersatz) Key

- Wenn Primary Keys keinen Bezug auf echte Eigenschaften haben, z.B eine zufällige Nummer in der User Tabelle, wird dieser als "Surrogate Key" bezeichnet
