# Ex No:1b  IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## AIM:
  To Implement of sliding window protocal.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### CLIENT
```py
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
size=int(input("Enter number of frames to send : ")) 
l=list(range(size)) 
s=int(input("Enter Window Size : ")) 
st=0 
i=0 
while True: 
    while(i<len(l)): 
            st+=s 
            c.send(str(l[i:st]).encode()) 
            ack=c.recv(1024).decode() 
            if ack: 
                print(ack) 
                i+=s 

```
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
### CLIENT OUTPUT:

![Screenshot 2024-11-21 174404](https://github.com/user-attachments/assets/612494ab-8499-4ec6-acef-255cc939cb00)

### SERVER OUTPUT:

![Screenshot 2024-11-21 174348](https://github.com/user-attachments/assets/4eb45939-876c-4cd4-a13d-01e7c85c06a9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
