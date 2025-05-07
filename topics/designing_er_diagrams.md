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

#### Branch Entity

<img width="466" alt="Bildschirmfoto 2025-05-07 um 10 38 42" src="https://github.com/user-attachments/assets/f9b9ba01-1ea6-4844-bde2-f414d2177e75" />

- Die Branch Entity hat einen branch_name und eine branch_id als Attribut. Die branch_id ist der Primary Key.

#### Client Entity

<img width="489" alt="Bildschirmfoto 2025-05-07 um 10 39 19" src="https://github.com/user-attachments/assets/68b64498-8379-4fbc-bd67-47d6dad00c66" />

- Die Client Entity hat einen client_name und client_id als Attribut. Die client_id ist der Primary Key.

#### Employee Entity

<img width="578" alt="Bildschirmfoto 2025-05-07 um 10 39 58" src="https://github.com/user-attachments/assets/ab934ef8-be43-48b8-9639-5e03497c9c29" />

- Die Employee Entity hat neben weiteren Attributen einen age Attribut. Dieses ist ein 'Derived Attribute' und entsteht aus dem birth_date Attribut.

#### Relationship between employee and branch (Works For)

<img width="1440" alt="Bildschirmfoto 2025-05-07 um 10 41 28" src="https://github.com/user-attachments/assets/2c15152c-1cf5-498e-ab69-89f2518e16e2" />

- Jeder employee muss für einen branch arbeiten und jeder branch hat employees die für den branch arbeiten
  (Full Participation bei beiden)
- Jeder employee kann für einen branch arbeiten, jeder branch kann beliebig viele Mitarbeiter haben.

#### Relationship between employee and branch (Manages)

<img width="1302" alt="Bildschirmfoto 2025-05-07 um 10 47 20" src="https://github.com/user-attachments/assets/1fafa3b1-ceed-46bb-afcb-3f2a111ea2f0" />

#### Relationship between employees (Supervision)

<img width="1474" alt="Bildschirmfoto 2025-05-07 um 10 51 40" src="https://github.com/user-attachments/assets/db429cd7-8b1d-429e-b1cf-81f72b3e5d49" />

#### Relationship between branch and client (Handles)

<img width="1481" alt="Bildschirmfoto 2025-05-07 um 10 54 22" src="https://github.com/user-attachments/assets/be00e776-7b01-47fc-9cd0-8afb0e54db6b" />

#### Relationship between employees and clients (Works with)

<img width="1475" alt="Bildschirmfoto 2025-05-07 um 10 58 12" src="https://github.com/user-attachments/assets/4c08c647-ca38-4459-930c-2a56a105aabe" />

#### Relationship between branch and branch supplier (Supplies)

<img width="1472" alt="Bildschirmfoto 2025-05-07 um 11 07 02" src="https://github.com/user-attachments/assets/5d04b9c9-2fea-41b1-9ded-6c00cf27f140" />
