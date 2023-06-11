# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## DATE :

## AIM :

To write a python program to perform sliding window protocol


## ALGORITHM :

- Start the program.
- Get the frame size from the user
- To create the frame based on the user request.
- To send frames to server from the client side.
- If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
- Stop the program

## PROGRAM :


## CLIENT:
```
## Developed : MIDHUN AZHAHU RAJA P
## Reg no : 212222240066

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

## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode()
 ```

## OUTPUT :

![EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL](https://github.com/kannan0071/EX-3/assets/119641638/cc12f131-5805-431e-9922-a8dfd3780c54)


## RESULT:


  Thus, python program to perform stop and wait protocol was successfully executed.
