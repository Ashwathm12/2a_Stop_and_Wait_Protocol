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
# client:
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
# server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
# client:
![2aclient](https://github.com/Ashwathm12/2a_Stop_and_Wait_Protocol/assets/138849225/5489d72c-4f59-449a-8454-082e56fe8631)


# server:
![2aserver](https://github.com/Ashwathm12/2a_Stop_and_Wait_Protocol/assets/138849225/8acdb107-f357-4268-9f6a-c4b8282c877e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
