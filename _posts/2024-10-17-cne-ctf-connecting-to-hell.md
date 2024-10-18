---
layout: post
title: CnE CTF 2024 - Coding 02 - Connecting to Hell
---
```py
import socket

# Server's IP address and port
SERVER_IP = '127.0.0.1'
SERVER_PORT = 666  # Doom port

# Create a TCP/IP socket
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect the socket to the server's address and port
sock.connect((SERVER_IP, SERVER_PORT))

# Receive data from the server
data = sock.recv(1024)

# Print the received data (flag)
print("Received data:", data)

# Close the socket
sock.close()
```

```
PS C:\Users\1dust\Documents\repos\1dgk.github.io> & C:/Users/1dust/AppData/Local/Microsoft/WindowsApps/python3.11.exe c:/Users/1dust/Downloads/CnE_CTF_2024/Coding_02_Connecting_to_Hell.py
Received data: b'The portal has been open!! Hell has been set free!!  CnE{h0w_c0u1d_h311_b3_4ny_w0rs3}'
```

```
Hell has been contacted!
It is ready for you.
The portal is waiting to be open...
Connect to your DOOM port and surrender your world...
/|       |\
| \/^^^\/ |
\_/"\ /"\_/
  | O O |
  |  V  |
  \ /"\ /
   \___/

The portal has been open!! Hell has been set free!!
The flag has been sent to you

Press return to exit
```