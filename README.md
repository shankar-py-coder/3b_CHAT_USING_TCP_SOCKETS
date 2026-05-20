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
```
Client:
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    if msg.lower() == "exit":
        break
    s.send(msg.encode())
    reply = s.recv(1024).decode()
    print("Server >", reply)
s.close()

Server:
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for client connection...")
c, addr = s.accept()
print("Connected to:", addr)
while True:
    client_message = c.recv(1024).decode()
    if not client_message:
        break
    print("Client >", client_message)
    msg = input("Server > ")
    if msg.lower() == "exit":
        break
    c.send(msg.encode())
c.close()
s.close()
```

## OUPUT
Client:

<img width="610" height="143" alt="Screenshot 2026-05-20 134241" src="https://github.com/user-attachments/assets/4902c0eb-bff1-4b42-b981-71d98063d134" />


Server:

<img width="630" height="218" alt="Screenshot 2026-05-20 134226" src="https://github.com/user-attachments/assets/4236868a-8a79-4e5a-a4b8-cb79cd0108f5" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
