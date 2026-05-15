---
tags:
  - cyber/Security_Operations
Date /Time: "{date} {time}"
title:
---
The Data Life Cycle is a framework that describes the stages data goes through from its initial generation to its eventual deletion. Managing this cycle properly ensures that data remains useful, secure, and compliant with laws like [[GDPR]].

### 1. Creation or Collection

This is the starting point where data enters the system. It can be **generated** internally (like an invoice), **collected** from customers (like a web form), or **acquired** from third parties (like a research database).
- **Key Concern:** Data quality and accuracy. If the data is "garbage" at the start, it stays "garbage" throughout.
### 2. Storage and Maintenance

Once data exists, it must be housed in a secure environment. This involves setting up databases, cloud storage, or physical servers.
- **Key Concern:** Security and redundancy. You need encryption to keep it safe and backups to ensure it isn’t lost in a system crash.
### 3. Usage

This is where the data provides value. It is processed, viewed, and used to make business decisions, run applications, or fulfill customer requests.
- **Key Concern:** Access control. Only people who _need_ the data to do their jobs should be able to access it (the [[Principle of Least Privilege]]).
### 4. Sharing and Publication

Data often needs to leave its original silo. This could mean sending a report to a client, sharing data between internal departments, or making it public.
- **Key Concern:** Data leakage. Once data is shared outside your immediate control, the risk of it being misused increases significantly.
### 5. Archiving

When data is no longer needed for daily operations but must be kept for legal, regulatory, or historical reasons, it is moved to "cold storage." This is cheaper than active storage but still keeps the data retrievable.
- **Key Concern:** Long-term integrity. Will the hardware or file format still be readable 10 years from now?
### 6. Destruction (Purging)

Every piece of data should eventually be destroyed to reduce liability and storage costs. This isn't just "hitting delete"—it involves secure erasure or physical destruction of hardware.
- **Key Concern:** Compliance. If you delete data too early, you might break the law; if you keep it too long, you're a bigger target for hackers.