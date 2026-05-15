---
tags:
  - cyber/Security_Operations
Date /Time: "{date} {time}"
title:
---
Encryption uses complex mathematical algorithms to rearrange bits of data. Without the correct key, the scrambled data looks like a random string of characters, making it useless to hackers or eavesdroppers.

## Symmetric & Asymmetric Encryption

There are two primary ways encryption is handled in modern computing

|**Type**|**Description**|**Key Usage**|
|---|---|---|
|**Symmetric**|The same key is used to both encrypt and decrypt the data.|**One Key:** Fast and efficient, but both parties must safely share the key first.|
|**Asymmetric**|Uses a pair of keys: a **Public Key** (to encrypt) and a **Private Key** (to decrypt).|**Two Keys:** More secure for the internet because you never have to share your private key.|
## Hashing 

Hashing takes an input (a file, a password, or a sentence) and runs it through a mathematical function to produce a fixed-size string of characters, called a **hash**.
### Key Characteristics

Hashing is unique because it is designed to be a "one-way street."

- **Deterministic:** The same input will _always_ produce the exact same hash.
- **Irreversible:** You cannot "un-hash" a string to see the original data.
- **Unique (The Avalanche Effect):** Even a tiny change to the input (like changing a capital "A" to a lowercase "a") will result in a completely different hash.
- **Fixed Length:** Whether you hash a single word or an entire encyclopedia, the output hash is always the same length (e.g., 64 characters for SHA-256).