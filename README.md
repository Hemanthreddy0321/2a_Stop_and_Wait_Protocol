# 2a_Stop_and_Wait_Protocol

Name: HEMANTH A
Reg.NO: 212223220035

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

CLIENT :
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
SERVER:
```
    import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT

CLIENT  :

![image](https://github.com/Hemanthreddy0321/2a_Stop_and_Wait_Protocol/assets/150005937/8a26e894-62eb-41ce-8301-bbbb580ae1cb)



SERVER :


!![image](https://github.com/Hemanthreddy0321/2a_Stop_and_Wait_Protocol/assets/150005937/02a78b4e-71c9-43cf-80c2-f436c2da8acf)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
