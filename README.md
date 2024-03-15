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
CLIENT
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
SERVER
```
   import socket
   s=socket.socket()
   s.connect(('localhost',8000))
   while True:
      print(s.recv(1024).decode())
      s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT:

![Screenshot 2024-03-15 125257](https://github.com/karthickkumar-R/2a_Stop_and_Wait_Protocol/assets/150005103/12b4647f-f5cf-4de5-92e1-23242e22e158)


SERVER:

![Screenshot 2024-03-15 125312](https://github.com/karthickkumar-R/2a_Stop_and_Wait_Protocol/assets/150005103/6c42a739-4c1b-43b0-9ad1-b8e0106fbd89)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
