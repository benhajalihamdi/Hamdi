---
tags:
  - cyber/Security_Operations
Date /Time: "{date} {time}"
title:
---
## [[Encryption]]

## Data Handling

This is the logistical side of the [[Data Life Cycle]]. It ensures that data is treated with the correct level of respect based on its sensitivity.

## Logging and Monitoring

If encryption is the "lock" on the door, logging and monitoring are the **security cameras** and the **security guard** watching them.
#### **Logging**
Every time someone logs in, accesses a file, or changes a setting, the system creates a **Log Entry**.

- **What is recorded?** The "Who, What, Where, and When" of an event.
- **Why it matters:** If a breach happens, logs are the "breadcrumbs" investigators use to see how the hacker got in.
#### **Monitoring**
This is the active process of reviewing those logs in real-time.
- **SIEM (Security Information and Event Management):** A tool that collects logs from every computer in a company and uses AI to spot weird patterns (e.g., "Why is Bob logging in from Russia at 3:00 AM?").
- **Alerting:** When a suspicious event is detected, the system sends an immediate alert to the security team