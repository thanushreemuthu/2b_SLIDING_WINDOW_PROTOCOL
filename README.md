# REG NO: 212224240169 NAME: Thanushree M
# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames of send:"))
l=list(range(size))
s=int(input("Enter Window size:"))
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
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
![Screenshot (68)](https://github.com/user-attachments/assets/c07a4a9a-034a-4a14-b11c-d03e0c8c0075)
![Screenshot (69)](https://github.com/user-attachments/assets/402aee1f-f0ef-4a8b-bfeb-3fbb36b84158)

## RESULT
Thus, the implementation of sliding window was successfully executed
