---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---

**XOR encoding** (or XOR encryption) is a simple, lightweight method of obfuscating or encrypting data using the logical **Exclusive OR (XOR)** operation.

$$Data⊕Key=Encoded Data$$

$$Encoded Data⊕Key=Data$$

To XOR a text string, computers do exactly what they always do under the hood: **they convert the letters into numbers first.** Every letter, number, and punctuation mark on your keyboard corresponds to a specific number defined by character encoding standards like **ASCII** or **UTF-8**.

Once the string is converted into those numbers (and subsequently into binary), the XOR operation happens byte-by-byte.

If you want to encode a whole string, you usually use a **repeating key**. If your key is shorter than your message, you just loop the key over and over until the message is finished.

Let's look at how the message **"SECRET"** gets encoded using the 3-letter key **"KEY"**: