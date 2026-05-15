---
tags:
  - cyber/BC-DR-Incident-response
Date /Time: "{date} {time}"
title:
---

### 1. Core Objectives

In DR, success is measured by two critical metrics that determine how much pain the business can endure:

- **Recovery Time Objective (RTO):** The maximum amount of **time** a system can be down before the damage is irreparable. (e.g., "We must have email back online within 4 hours.")
- **Recovery Point Objective (RPO):** The maximum amount of **data** you can afford to lose, measured in time. (e.g., "If we lose more than 15 minutes of bank transactions, we are in trouble.")
### 2. The DR Process

A standard DR plan follows a sequence of events to move from "Total Failure" back to "Business as Usual":
1. **Detection & Activation:** Identifying that a disaster has occurred and formally declaring a "DR event" to mobilize the team.
2. **Containment:** Stopping further damage.
3. **System Restoration:** Recovering data from backups and spinning up virtual servers.
4. **Verification:** Testing the restored systems to ensure data is consistent and the applications actually work.
5. **Failback:** The final step of moving operations from the emergency "backup" site back to the primary location once it's repaired.