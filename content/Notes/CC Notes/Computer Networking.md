---
tags:
  - cyber/Networking
Date /Time: "{date} {time}"
title:
---
## 1. Network Models: OSI vs. TCP/IP

These models act as blueprints for communication. The **OSI Model** is the theoretical standard used for teaching, while the **TCP/IP Model** is the practical architecture used by the actual internet.

### The OSI Model (7 Layers)

1. **Physical:** Hardware, cables, and bits (0s and 1s).
2. **Data Link:** MAC addresses and switches.
3. **Network:** IP addresses and routers.
4. **Transport:** Ensures data arrives correctly (TCP/UDP).
5. **Session:** Manages the connection between applications.
6. **Presentation:** Translation, encryption, and compression.
7. **Application:** The interface the user interacts with (HTTP, FTP).


## 2. IP Addressing: IPv4 vs. IPv6

Every device on a network needs a unique address. Think of it like a mailing address for your computer.

|**Feature**|**IPv4**|**IPv6**|
|---|---|---|
|**Format**|32-bit (e.g., `192.168.1.1`)|128-bit (e.g., `2001:0db8:85a3...`)|
|**Total Addresses**|~4.3 Billion (We've run out!)|340 Undecillion (Virtually infinite)|
|**Security**|Optional add-ons|Designed with security (IPsec) in mind|
|**Configuration**|Usually manual or DHCP|Self-configuring (Stateless)|

## 3. WiFi (IEEE 802.11)

WiFi is the standard for wireless local area networking. It uses radio waves (usually **2.4GHz** for range or **5GHz/6GHz** for speed) to transmit data.

- **Security Protocols:** You’ll see terms like **WPA2** or **WPA3**. These are the "encryption envelopes" that keep your wireless data from being intercepted by neighbors.



##  4. Ports: The Digital Doorways

If an **IP Address** is the address of an apartment building, a **Port** is the specific apartment number. Each type of internet traffic goes through a specific port.

- **Port 80:** HTTP (Unsecured web traffic).
- **Port 443:** HTTPS (Secured web traffic).
- **Port 22:** SSH (Secure login to other computers).
- **Port 25:** SMTP (Sending emails).

## 5. Applications

In networking, the "Application" layer isn't just the app on your phone; it's the **protocol** that the app uses to communicate.
- **Web Browsers** use **HTTP/HTTPS**.
- **Email Clients** use **IMAP/POP3** to receive mail.
- **File Transfer Tools** use **FTP** or **SFTP**.