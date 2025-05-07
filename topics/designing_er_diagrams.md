## Disigning ER Diagrams

- Zu Beginn bekommt man eine Beschreibung der Daten und die Beziehungen zwischen den Daten, die dann zum Schluss zu einem Database Schema konvertiert werden soll
- Mit dieser Beschreibung kann man davor ein ER Diagram erstellen und dieses dann in ein Database Schema kovertieren.

### Data Requirements

1. The company is organized into **branches**. Each branch has a **unique number**, a **name** and a particular **employee** who manages it.

2. The company makes it's money by selling to **clients**. Each client has a **name** and a unique **number** to identify it.

3. The foundation of the company is it's **employees**. Each employee has a **name**, **birthday**, **sex**, **salary**, and a **unique number**.

4. An **employee** can work for **one branch at a time**, and each **branch** will be managed by **one of the employees** that work there. We'll also want to keep track of when the current manager started as manager.

5. An **employee** can act as a **supervisor for other employees at the branch**, an employee may also act as the supervisor **for employees at other branches**. An employee can have **at most one supervisor**.

6. A **branch** may handle a **number of clients**, with each client having a name and a unique number to indetify it. A **single client** may only be handled by **one branch at a time**.

7. **Employees** can work with clients controlled by their branch to sell them stuff. If neccessary **multiple employees** can work with the **same client**. We'll want to keep track of how many **dollars worth of stuff** each **employee** sells to each **client** they work with.

8. Many **branches** will need to **work with suppliers** to buy inventory. For each supplier we'll keep track of their name and the type of product they're selling the branch. A **single supplier** may supply products to **multiple branches**.

### ER Diagram Steps

- Branch Entity
<img width="466" alt="Bildschirmfoto 2025-05-07 um 10 38 42" src="https://github.com/user-attachments/assets/f9b9ba01-1ea6-4844-bde2-f414d2177e75" />

- Client Entity
<img width="489" alt="Bildschirmfoto 2025-05-07 um 10 39 19" src="https://github.com/user-attachments/assets/68b64498-8379-4fbc-bd67-47d6dad00c66" />

- Employee Entity
<img width="578" alt="Bildschirmfoto 2025-05-07 um 10 39 58" src="https://github.com/user-attachments/assets/ab934ef8-be43-48b8-9639-5e03497c9c29" />

- Relationship between employee and branch (Works For)
<img width="1440" alt="Bildschirmfoto 2025-05-07 um 10 41 28" src="https://github.com/user-attachments/assets/2c15152c-1cf5-498e-ab69-89f2518e16e2" />

- Relationship between employee and branch (Manages)

// screenshot

- Relationship between employees (Supervision)

// screenshot

- Relationship between branch and client (Handles)

// screenshot

- Relationship between employees and clients (Works with)

// screenshot

- Relationship between branch and branch supplier (Supplies)

// screenshot
