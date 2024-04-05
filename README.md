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
## PROGRAM:
## client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter the data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close
        break
```
## server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT:
## client:
![image](https://github.com/Rajaraman77/2a_Stop_and_Wait_Protocol/assets/150319383/77cb545e-62fb-4c63-a8d8-324d21bdbe2b)
## server:
![image](https://github.com/Rajaraman77/2a_Stop_and_Wait_Protocol/assets/150319383/e9bc0e5e-22df-482b-8781-67a65eef0b9e)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
