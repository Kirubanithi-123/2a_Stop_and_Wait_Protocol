# NAME: KIRUBANITHI.S
# REG No.:212223220047
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
## SERVER:
import socket

s = socket.socket()

s.bind(('localhost',8000))

s.listen(5)

c,addr = s.accept()

while True:

    i = input("Enter a message: ")
    
    c.send(i.encode())
    
    ack = c.recv(1024).decode()
    
    if ack:
    
        print(ack)
        
        continue
    
    else:
    
        c.close()
        
        break

## CLIENT:

import socket

s=socket.socket()

s.connect(('localhost',8000))

while True:

    print(s.recv(1024).decode())
    
    s.send("Acknowledgement Recived".encode())

## OUTPUT

![Screenshot 2024-04-05 105815](https://github.com/Kirubanithi-123/2a_Stop_and_Wait_Protocol/assets/151388581/b1c5a3b5-a3fb-4f46-9203-0d7d50a83b02)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
