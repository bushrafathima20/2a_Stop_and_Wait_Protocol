# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Client.py:

```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode())  
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break
```
## Server.py:

```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
  print(s.recv(1024).decode()) 
  s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client.py:

<img width="833" height="900" alt="Screenshot 2026-05-21 134342" src="https://github.com/user-attachments/assets/9d1e5290-1050-4db4-a8bc-a6ecd7cf7399" />

## Server.py:

<img width="922" height="887" alt="Screenshot 2026-05-21 134425" src="https://github.com/user-attachments/assets/2c73b7f1-820a-4800-9692-365d1aaa0b20" />

## Developed By: BUSHRA FATHIMA I
## Register Number: 212225040051

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
