---
tags:
aliases:
  - pentesting
date/time: 2026-03-29 17:10
Date /Time: "{date} {time}"
title:
draft: true
---
**Penetration testing** (often called "pen testing" or ethical hacking) is a simulated, authorized cyberattack on a computer system, network, or web application to find security weaknesses that malicious hackers could exploit.

Think of it like hiring a professional lockpicker to break into your house. Their job is to find the weak points—like an unlocked window or a flimsy back door—and tell you how to fix them before a real burglar shows up.

---

### The 5 Phases of a Penetration Test

A professional pen test isn't just randomly typing commands; it follows a strict methodology:

1. **Reconnaissance (Information Gathering):** The attacker gathers as much public information as possible about the target (IP addresses, employee emails, domain details).
    
2. **Scanning:** Using tools to map out the network, find open ports, and identify what software (and versions) the target is running.
    
3. **Exploitation (Gaining Access):** This is the actual "hack." The tester uses the vulnerabilities found in step 2 to break into the system, bypass security, or intercept traffic.
    
4. **Post-Exploitation (Maintaining Access):** Once inside, the tester sees how much damage they _could_ do. Can they steal sensitive databases? Can they create a backdoor to stay hidden? Can they compromise the rest of the network?
    
5. **Analysis and Reporting:** This is the most important part. The tester creates a detailed report showing exactly what they found, how they broke in, and step-by-step instructions on how the company can patch the holes.
    

---

### The 3 Main Types of Pen Tests

Depending on what a company wants to test, they will give the ethical hacker different levels of information:

| Type          | What It Is                                                                                                       | Real-World Equivalent                                                                               |
| ------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Black Box** | The tester is given **zero information** about the target system (only the company name or a website URL).       | Simulates an attack from a random, outside hacker on the internet.                                  |
| **Gray Box**  | The tester is given **partial information**, like a set of standard user login credentials.                      | Simulates an insider threat, like an employee going rogue, or a customer account being compromised. |
| **White Box** | The tester is given **full access** to everything, including network maps, system architecture, and source code. | Used to conduct an exhaustive, deep-dive audit to ensure every single component is secure.          |
