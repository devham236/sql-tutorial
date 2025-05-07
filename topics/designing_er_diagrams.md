## Disigning ER Diagrams

- Zu Beginn bekommt man eine Beschreibung der Daten und die Beziehungen zwischen den Daten, die dann zum Schluss zu einem Database Schema konvertiert werden soll
- Mit dieser Beschreibung kann man davor ein ER Diagram erstellen und dieses dann in ein Database Schema kovertieren.

### Data Requirements

1. The company is organized into **branches**. Each branch has a **unique number**, a **name** and a particular **employee** who manages it.

2. The company makes it's money by selling to **clients**. Each client has a **name** and a unique **number** to identify it.

3. The foundation of the company is it's **employees**. Each employee has a **name**, **birthday**, **sex**, **salary**, and a **unique number**.

4. An **employee** can work for **one branch at a time**, and each branch will be managed by one of the employees that work there. We'll also want to keep track of when the current manager started as manager.
