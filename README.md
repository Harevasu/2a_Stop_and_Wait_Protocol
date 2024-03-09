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
### CLIENT:
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
### SERVER:
```import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
![Screenshot 2024-03-09 112629](https://github.com/Harevasu/2a_Stop_and_Wait_Protocol/assets/147985044/e3b45dc8-90cb-443e-8d02-e43f03327908)
![Screenshot 2024-03-09 112759](https://github.com/Harevasu/2a_Stop_and_Wait_Protocol/assets/147985044/046b57f1-6fc1-473b-acae-40f58f6b31d4)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
