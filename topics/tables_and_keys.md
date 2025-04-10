## Tables and Keys

- Eine Tabelle besteht aus Spalten (columns) und Reihen (rows)
- Eine Spalte beschreibt die ein einzelnes Attribut bzw. eine einzelne property.
- Eine Reihe (rows) beschreibt einen gesamten Eintrag in der DB
  <img width="680" alt="Bildschirmfoto 2025-04-10 um 10 29 23" src="https://github.com/user-attachments/assets/38e396c7-f383-4cf6-88ce-36c3fa850d73" />

- Wenn man eine Tabelle erstellen möchte sollte jede Reihe einen einzigartigen Wert besitzen um sich immer von allen zu unterscheiden.
- Deswegen sollte es immer eine Id Spalte geben.
- Dieser einzigartige Wert wird auch als "Primary Key" bezeichnet.

### Natural Key

- Primary Keys können einen Bezug auf reale Eigenschaften haben, z.B in einer User Tabelle wird die Email Adresse als Primary Key verwendet oder die IBAN eines Benutzers in einer Kunden Tabelle für eine Bank, hier werden diese Keys als "Natural Keys" bezeichnet

### Surrogate(Ersatz) Key

- Wenn Primary Keys keinen Bezug auf echte Eigenschaften haben, z.B eine zufällige Nummer in der User Tabelle, wird dieser als "Surrogate Key" bezeichnet

### Foreign Key

- Wir können in jeder Reihe auch einen weiteren Primary Key definieren, dieser verweist auf Primary Keys einer anderen Tabelle.
- Dieser Verweis funktioniert bidirektional, in der Branch Tabelle verweisen wir mit der "mgr_id" auf die "emp_id" in der Employee Tabelle.
- Aus der Branch Tabelle erfahren wir das Michael Scott der Manager für den Branch Scranton ist.
  <img width="912" alt="Bildschirmfoto 2025-04-10 um 11 00 49" src="https://github.com/user-attachments/assets/6b633c5e-8281-41b8-b32e-2abb7eb45379" />
  <img width="395" alt="Bildschirmfoto 2025-04-10 um 11 01 18" src="https://github.com/user-attachments/assets/c4572885-12b4-4caa-bc64-0ccf3aafad5c" />

### Composit Key

- Composit Keys bestehen aus mehreren Primary Keys, weil ein einzelner die Reihe nicht einzigartig identifizieren würde.
  <img width="410" alt="Bildschirmfoto 2025-04-10 um 11 16 16" src="https://github.com/user-attachments/assets/2c0ead3f-2e0b-4757-9b40-bce2e5b2a3e6" />
- Diese Keys können auch aus mehreren Foreign Keys bestehen
<img width="1079" alt="Bildschirmfoto 2025-04-10 um 11 24 36" src="https://github.com/user-attachments/assets/14f20aec-b610-4133-9223-f64a5fdf6541" />


