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
server.py
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
client.py
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
<img width="434" height="135" alt="image" src="https://github.com/user-attachments/assets/1a42f5d5-f1cb-4375-b515-d539e8db6a8a" />
<img width="498" height="131" alt="image" src="https://github.com/user-attachments/assets/005f179c-84c2-401b-99cc-5a4b66f7fe07" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
