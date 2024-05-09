# Ex No:2b  IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : ARAVINDAN D
## REGISTER NUMBER : 212223240012
## AIM
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
c, addr=s. accept()
size=int(input ("Enter number of frames to send"))
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

![Screenshot 2024-05-09 124200](https://github.com/Aravindan2006/2b_SLIDING_WINDOW_PROTOCOL/assets/151760062/7fec0bf4-decf-49cf-ad61-dd7a707b7a86)

### SERVER OUTPUT:

![Screenshot 2024-05-09 124208](https://github.com/Aravindan2006/2b_SLIDING_WINDOW_PROTOCOL/assets/151760062/bed5fa72-6966-4d9f-9d0e-0d9000011dd9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
