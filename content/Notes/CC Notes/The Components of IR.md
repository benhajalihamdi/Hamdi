---
tags:
  - cyber/BC-DR-Incident-response
Date /Time: "{date} {time}"
title:
---
The industry standard for IR is the **SANS Institute** or **NIST** 6-step process:

### **1. Preparation**

The most critical phase. This involves building the **Incident Response Team (IRT)**, establishing communication channels, and ensuring all security tools (like logs and backups) are functional _before_ an incident happens.

### **2. Identification (Detection)**

Using monitoring tools (SIEM) or user reports to determine if an event is a false alarm or a genuine security incident.

### **3. Containment**

The "Triage" phase. Once an incident is confirmed, the goal is to stop it from spreading.

- **Short-term:** Isolate the infected laptop from the WiFi.
- **Long-term:** Patch the server or shut down a specific network segment.

### **4. Eradication**

After the threat is contained, you find the "root cause" and remove it. This might involve deleting malware, disabling compromised user accounts, or cleaning up malicious code.

### **5. Recovery**

Restoring systems to normal operation. This phase includes verifying that the systems are clean and monitoring them closely to ensure the attacker doesn't try to come back immediately.

### **6. Lessons Learned (Post-Incident)**

The team meets to discuss the results are used to update the **Preparation** phase for the future.