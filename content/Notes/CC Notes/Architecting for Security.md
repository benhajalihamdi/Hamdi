---
tags:
  - cyber/Networking
Date /Time: "{date} {time}"
title:
---
 Modern design focuses on keeping different types of traffic separated.
 - **Network Access Control (NAC):** A system that checks a device's "health" before letting it connect.
    - **IoT/Embedded Systems:** NAC is vital here to isolate  devices (like smart lightbulbs or industrial sensors) into their own restricted segments so they can't be used to jump into sensitive databases.

- **Network Segmentation:**
    - **VLAN (Virtual Local Area Network):** Grouping devices logically (e.g., HR, Accounting, Guest) even if they are plugged into the same physical switch.
    
    - **DMZ (Demilitarized Zone):** A sub-network that sits between the private internal network and the public internet. It houses "public-facing" servers (like web or email servers).
    
    - **VPN (Virtual Private Network):** An encrypted connection that allows remote users to securely join the internal network over the public internet.
    
    - **Micro-segmentation:** Granular security that manages traffic between individual workloads (often in the cloud) to prevent lateral movement by attackers.

- **Defense in Depth:** The strategy of using multiple layers of security:

Firewalls → Antivirus → Encryption → User Training.
If one layer fails, the next one stops the threat.
