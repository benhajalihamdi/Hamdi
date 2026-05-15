---
tags:
Date /Time: "{date} {time}"
title:
---
The **Principle of Least Privilege (PoLP)** is a security concept where a user, program, or process is given only the minimum permissions necessary to perform its specific function.
### **Purpose**

- **Limit the "Blast Radius":** If an account is compromised, the attacker only gains access to the limited resources that specific user was allowed to touch.
- **Prevent Insider Threats:** It stops employees from accessing sensitive data (like payroll or HR files) that they don't need for their daily tasks.
- **Reduce Human Error:** Users cannot accidentally delete or modify critical system files if they don't have the "Write" or "Delete" permissions for those files.

### **Importance**

- **Security:** It is one of the most effective ways to stop "lateral movement," where a hacker jumps from one low-level account to more sensitive systems.
- **Compliance:** Most security frameworks (like NIST, ISO 27001, and [[GDPR]]) require PoLP to protect sensitive personal and corporate data.

### **Implementation**

- **Just-in-Time (JIT) Access:** Providing elevated permissions only when needed and for a limited time.
- **Regular Audits:** Periodically reviewing user rights to remove "privilege creep" (permissions accumulated over time as roles change).
- **Role-Based Access Control (RBAC):** Assigning permissions to a "Role" (e.g., Accountant) rather than an individual, ensuring everyone in that role has the same