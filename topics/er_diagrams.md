## ER Diagrams (Entity Relationship)

- Mit ER Diagrammen kann man den Aufbau und die Beziehungen zwischen den Tabellen (Entities) anhand von Database Schemas darstellen

### Entity (Entität)

- Eine Entity beschreibt ein Objekt welches verschiedene Informationen in einer rechteckigen Form enthalten kann, beschreibt meist eine Tabelle.

<img width="353" alt="Bildschirmfoto 2025-05-03 um 14 56 22" src="https://github.com/user-attachments/assets/a8467170-0e23-492d-9996-d0bc41a451b5" />

### Attributes (Attribute)

- Attribute beschreiben bestimmte Informationen bzw. Attribute einer Entität, z.B die einzelnen Spalten/Columns die eine Tabelle beinhalten soll. Sie werden in einer ovalen Form angezeigt

// screenshot

### Primary Key

- Mit dem Primary Key können wir auf einzelne Einträge zugreifen um gezielt nur einen bestimmten Eintrag auszuwählen.

// screenshot

### Composit Attributes

- Ein Attribut das sich in weitere Sub-Attribute aufteilen kann

// screenshot

### Multi-valued Attribute

- Ein Attribut das mehr als nur einen Wert haben kann.

// screenshot

### Relationships between Entities

- Die Linien zwischen den Entities 'Student'/'Class' und der Beziehung 'Takes' beschreiben die Partizipation der Entities.
- Nicht jeder Student muss einen Kurs/Class besuchen (partial participation)
- Jeder Kurs muss aber von mindestens einem Studenten besucht werden (total participation)

// screenshot

### Relationship Attribute

- Ein Attribute über die Beziehung.

// screenshot

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
