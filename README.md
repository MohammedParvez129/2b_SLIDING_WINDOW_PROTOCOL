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
CLIENT: 
 ```
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
SERVER: 
 ```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
 

while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode()) 
 ```
## OUPUT




![Screenshot 2024-02-28 201254](https://github.com/MohammedParvez129/2b_SLIDING_WINDOW_PROTOCOL/assets/143175737/b5fb1975-a36d-4502-a4e0-cc464189e2eb)


![Screenshot 2024-02-28 201308](https://github.com/MohammedParvez129/2b_SLIDING_WINDOW_PROTOCOL/assets/143175737/9de445f0-828c-4ee3-88b1-fd0e271d2e88)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
