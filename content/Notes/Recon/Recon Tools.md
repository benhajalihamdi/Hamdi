---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---

Active Recon for a TCP handshake:
```
Attacker Machine               Target Server
      |                              |
      | ------ SYN (Hello?) -------> |
      |                              | (If Port is OPEN)
      | <--- SYN-ACK (I'm here) ---- | 
      |                              |
      | ------ ACK (Got it!) ------> |
```

1. **The Probe:** The recon tool sends a `SYN` (synchronize) packet to Port 80.
2. **The Response:** If the port is **open**, the server responds with a `SYN-ACK` (synchronize-acknowledge). If the port is **closed**, the server responds with a `RST` (reset) packet.
3. **The Conclusion:** The recon tool logs the response and reports back to the hacker: _"Port 80 is open, meaning there is likely a web server running here."_


## NetCat
| **Flag**    | **Description**                                                                        |
| ----------- | -------------------------------------------------------------------------------------- |
| `-l`        | **Listen** mode (acts as a server waiting for incoming connections)                    |
| `-p [port]` | Specifies the **Port** number                                                          |
| `-v`        | **[[Verbose]]** mode (gives more details about the connection)                         |
| `-n`        | Numeric-only IP addresses (skips **[[DNS resolution]]** to speed things up)            |
| `-u`        | Uses **UDP** instead of the default TCP                                                |
| `-w [secs]` | **Timeout**; cuts the connection after a specified number of seconds                   |
| `-z`        | **Zero-I/O mode**; used for scanning (reports connection success without sending data) |


Computers don't naturally understand names like `google.com` or `facebook.com`. They only understand **IP addresses** (numbers like `142.250.190.46`).
**DNS (Domain Name System)** is the phonebook of the internet. It matches human-readable names to computer-readable numbers.
**DNS Resolution** is the actual process of looking up a name in that phonebook to find the number.