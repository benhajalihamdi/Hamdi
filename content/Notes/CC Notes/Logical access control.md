---
tags:
  - cyber/Access_Controls_Concepts
Date /Time: "{date} {time}"
title:
---
#### [[Principle of Least Privilege]]

This is the practice of giving a user the **minimum** levels of access needed to perform their job functions.
- **The Goal:** To limit the "blast radius." If an employee’s account is hacked, the attacker only gains access to the few things that specific employee was allowed to touch, rather than the entire network. 
#### **Segregation of Duties (SoD)**
This principle ensures that no single person has enough power to complete a critical process from start to finish without oversight.

- **The Goal:** To prevent fraud and errors.
- **Example:** The person who creates a vendor in the system should not be the same person who authorizes payments to that vendor.
### 2. Access Control Models

These are the different "logic styles" used to determine how permissions are assigned.
#### **Discretionary Access Control (DAC)**

In a DAC system, the **owner** of the data has total control over who else can access it.
- **How it works:** If you create a Google Doc, you are the owner. You "discretionarily" decide to give your teammate "View" or "Edit" rights.

#### **Mandatory Access Control (MAC)**

This is the strictest model, often used by military and high-security government agencies.

- **How it works:** Access is based on **labels** (e.g., Secret, Top Secret) and **clearances**. A central authority (the system admin) sets the rules, and the data owner cannot change them.

#### **Role-Based Access Control (RBAC)**

This is the most common model used in modern businesses today.

- **How it works:** Permissions are tied to **Roles** (e.g., "Manager," "HR Specialist," "IT Admin") rather than individuals. You assign an employee to a role, and they automatically inherit all the permissions that come with it.
