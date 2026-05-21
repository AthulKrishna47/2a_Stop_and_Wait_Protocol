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

Program developed by: Athul Krishna A V (212225240017)
### client.py
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
### server.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived frome the server".encode())
```
## OUTPUT

<b>client.py</b><br>
<img width="411" height="87" alt="Screenshot 2026-05-21 101119" src="https://github.com/user-attachments/assets/9fd5d8dc-fd0a-44ae-a3d5-a622231a72a1" />


<b>server.py</b><br>
<img width="251" height="142" alt="image" src="https://github.com/user-attachments/assets/981a1d54-ff1a-4e30-b343-d78c6899530b" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
