# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
## Name: Mugil Raj S A
## Register NO: 212223220062
# AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
# ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
# PROGRAM:
## Client:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))
```
## SERVER:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
# OUPUT:
## Client:

![Screenshot 2024-05-14 181830](https://github.com/MugilRaj1105/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/154905390/3d7fc112-b695-408b-8779-217cfb55c56a)

## Server:

![Screenshot 2024-05-14 181842](https://github.com/MugilRaj1105/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/154905390/e847fecb-d6a4-4d85-b2da-86ad63a6457f)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
