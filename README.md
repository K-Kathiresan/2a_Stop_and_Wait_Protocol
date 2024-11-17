# 2a_Stop_and_Wait_Protocol
## Name:Kathiresan K
## Reg no:212223110021
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
### Client
```python
###Name:Kathiresan K
###Reg no:212223110021
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
### Server
```python
###Name:Kathiresan K
###Reg no:212223110021
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### Client
<img width="623" alt="client" src="https://github.com/user-attachments/assets/9acf1287-39e9-480d-933f-7fe3b45fe3a9">

### Server
<img width="457" alt="server" src="https://github.com/user-attachments/assets/9a3894d2-3b5d-45fe-9b39-caeb2ac7532e">

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
