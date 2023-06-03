# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL
# AIM:
To write a python program to perform stop and wait protocol
# ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
# PROGRAM:
# CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',800))
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
# SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',800))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
# OUTPUT:
# CLIENT SIDE:
![Client 1 1](https://github.com/balar2004/19CS406-EX-2/assets/118791778/9eb2bb8c-4e10-49a6-b54e-83b3af1f11b1)
# SERVER SIDE:
![Server 1 1](https://github.com/balar2004/19CS406-EX-2/assets/118791778/fef27624-fbaa-4bcf-bc0d-f89ebc6e70cd)
# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
