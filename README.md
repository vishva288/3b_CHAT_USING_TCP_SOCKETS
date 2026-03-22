# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
Server.py
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Server is waiting for connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()
    print("Client >", msg)
    reply = input("Server > ")
    c.send(reply.encode())
```
Client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
```
## OUPUT
<img width="1035" height="641" alt="Screenshot 2026-03-22 132518" src="https://github.com/user-attachments/assets/024fc3a3-08bd-4263-9649-f4e16d597cee" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
