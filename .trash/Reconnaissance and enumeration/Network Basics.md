---
tags:
aliases:
date/time: "2026-03-20 14:50"
---

# 1. What a network actually is

A **network** is just devices connected together so they can communicate.

Examples:

- Your phone + router + laptop = small network
    
- The internet = massive network of networks
    

Each device needs:

- An **address** (to be identified)
    
- A **way to send/receive data**
    

---

# 2. IP addresses (identity of a device)

An **IP address** is like a home address for a device.

Example:

- `192.168.1.10` (typical local network IP)
    

### Two types you must know:

- **Private IP** (inside your home/network)
    
    - Examples: `192.168.x.x`, `10.x.x.x`
        
- **Public IP** (visible on the internet)
    

👉 Key idea:

- Devices inside a network talk using **private IPs**
    
- The outside world sees only your **public IP**
    

---

# 3. Ports (doors of a device)

A device doesn’t just have one entry—it has **many ports**.

Think:

- IP address = building
    
- Port = specific door
    

Examples:

- Port 80 → Web (HTTP)
    
- Port 443 → Secure web (HTTPS)
    
- Port 22 → SSH (remote login)
    
- Port 21 → FTP (file transfer)
    
- Port 445 → SMB (Windows sharing)
    

👉 In cybersecurity:

- Finding open ports = finding **entry points**
    

---

# 4. Protocols (rules of communication)

A **protocol** is the language devices use.

Common ones:

- HTTP → websites
    
- HTTPS → secure websites
    
- FTP → file transfer
    
- SSH → remote control
    
- DNS → converts names to IPs
    

Example:  
When you visit a website:

1. DNS finds the IP
    
2. HTTP/HTTPS loads the page
    

---

# 5. DNS (the internet’s phonebook)

Humans use names:

- `google.com`
    

Computers use IPs:

- `142.250.x.x`
    

**DNS converts names → IPs**

Without DNS, you'd have to memorize IP addresses.

---

# 6. Router (the traffic manager)

Your **router**:

- Connects you to the internet
    
- Assigns private IPs to devices
    
- Sends traffic to the right place
    

---

# 7. Basic communication flow (very important)

When you open a website:

1. Your device asks DNS: “What is the IP?”
    
2. DNS responds with IP
    
3. Your device sends a request to that IP on port 80/443
    
4. Server responds with data
    
5. You see the website
    

---

# 8. What you’ll do in cybersecurity

You’ll often:

- Find a device (IP)
    
- Check open ports
    
- Identify services
    
- Interact with them
    

Example:

- IP found → `192.168.1.5`
    
- Open port 22 → [[SSH]]
    
- Try to enumerate users or login behavior
    

---

# 9. Quick mental model (important)

Always think in this structure:

- **Who?** → IP address
    
- **Where?** → Port
    
- **How?** → Protocol
    

---

# 10. Tiny practical exercise (do this)

On your computer, open terminal and try:

- `ipconfig` (Windows) or `ifconfig` / `ip a` (Linux)  
    → See your IP
    
- `ping google.com`  
    → See communication working
    