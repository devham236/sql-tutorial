## ER Diagrams (Entity Relationship)

- Mit ER Diagrammen kann man den Aufbau und die Beziehungen zwischen den Tabellen (Entities) anhand von Database Schemas darstellen

### Entity (Entität)

- Eine Entity beschreibt ein Objekt welches verschiedene Informationen in einer rechteckigen Form enthalten kann, beschreibt meist eine Tabelle.

<img width="353" alt="Bildschirmfoto 2025-05-03 um 14 56 22" src="https://github.com/user-attachments/assets/a8467170-0e23-492d-9996-d0bc41a451b5" />

### Attributes (Attribute)

- Attribute beschreiben bestimmte Informationen bzw. Attribute einer Entität, z.B die einzelnen Spalten/Columns die eine Tabelle beinhalten soll. Sie werden in einer ovalen Form angezeigt

<img width="557" alt="Bildschirmfoto 2025-05-03 um 14 59 15" src="https://github.com/user-attachments/assets/c3cae97b-347d-4ff0-b49c-5dd111126bbe" />

### Primary Key
- Mit dem Primary Key können wir auf einzelne Einträge zugreifen um gezielt nur einen bestimmten Eintrag auszuwählen.

<img width="604" alt="Bildschirmfoto 2025-05-03 um 15 04 23" src="https://github.com/user-attachments/assets/5815c08a-f75b-460d-80bf-5e13ec10f58c" />

### Composit Attributes

- Ein Attribut das sich in weitere Sub-Attribute aufteilen kann

<img width="640" alt="Bildschirmfoto 2025-05-03 um 15 08 05" src="https://github.com/user-attachments/assets/b8df00ed-d06c-4912-b7ac-cf5258cf90e0" />

### Multi-valued Attribute

- Ein Attribut das mehr als nur einen Wert haben kann.

### Relationships between Entities

- Die Linien zwischen den Entities 'Student'/'Class' und der Beziehung 'Takes' beschreiben die Partizipation der Entities.
- Nicht jeder Student muss einen Kurs/Class besuchen (partial participation)
- Jeder Kurs muss aber von mindestens einem Studenten besucht werden (total participation)

<img width="1451" alt="Bildschirmfoto 2025-05-03 um 15 10 50" src="https://github.com/user-attachments/assets/e7250b58-0a43-4530-adab-87a553394b80" />

### Relationship Attribute

- Ein Attribute über die Beziehung.

<img width="1447" alt="Bildschirmfoto 2025-05-03 um 15 18 30" src="https://github.com/user-attachments/assets/d7610a01-0a20-4ced-8905-7659eddccf8e" />

### Relationship Cardinality

- Beschreibt die Anzahl an Instanzen einer Entität in Bezug auf die Beziehung
- N bedeutet ein Student kann x-beliebig viele Kurse besuchen
- M bedeutet ein Kurs kann von x-beliebig vielen Studenten besucht werden

- Wenn die Kardinalität der Beziehung 1:1 ist, kann ein Student einen Kurs besuchen und ein Kurs kann von einem Student besucht werden.
- 1:N bedeutet, der Student kann einen Kurs besuchen und ein Kurs kann von x-beliebig vielen Studenten besucht werden, oder andersrum.
- N:M bedeutet wie oben beschrieben.

// screenshot

### Weak Entities & Identifying Relationship

- Weak Entities sind Entities die nicht einzigartig durch die Attribute indetifiziert werden können, bedeutet eine Entity die abhängig von einer anderen Entity ist.
- Eine Identifying Relationship ist dazu da um eine weak Entity zu identifizieren.
- Eine Klausur existiert an sich nicht, nur in Abhängigkeit eines Kurses/Class

// screenshot
