---
layout: post
title: CnE CTF 2024 - Crypto 01
---
I used this site to calculate the symmetry key:

https://www.irongeek.com/diffie-hellman.php?

Then I used Copilot to create the from hex script:

```py
message = bytes.fromhex("c2efc4fae5b0e7e7b0b2dee9b2ededecb5efdef3f4b0b2f2fc")
symmetric_key = 129
xored_message = bytes([b ^ symmetric_key for b in message])
print(xored_message.decode('utf-8', errors='ignore'))
```