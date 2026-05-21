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
<img width="485" height="485" alt="Screenshot 2026-05-21 184259" src="https://github.com/user-attachments/assets/6b10be57-26ab-4383-898c-37e4b0dc80a6" />

<img width="767" height="267" alt="Screenshot 2026-05-21 183716" src="https://github.com/user-attachments/assets/401215b8-3964-411c-873b-e855fae299b3" />

## Server.py:
<img width="585" height="242" alt="Screenshot 2026-05-21 184412" src="https://github.com/user-attachments/assets/69d38893-bf0f-48c0-87a5-97fd1cf4cb72" />

<img width="712" height="240" alt="Screenshot 2026-05-21 183820" src="https://github.com/user-attachments/assets/de05a8e7-ad4b-4a4a-b0be-47bec247d25d" />

## Developed By: BUSHRA FATHIMA I
## Register Number: 212225040051

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
