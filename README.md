# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
CLIENT.PY
 ```
import socket
HOST = '127.0.0.1' 
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message (or 'exit' to quit): ")
        if message.lower() == 'exit':
            break
        s.sendall(message.encode())
        data = s.recv(1024)
        print(f"Echo from server: {data.decode()}")


```
SERVER.PY
```
import socket
HOST = '127.0.0.1' 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print(f"Server started. Listening on {HOST}:{PORT}...")
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)


```



## OUTPUT:
CLIENT.PY

<img width="707" height="768" alt="541393735-862f2c19-921d-422b-8479-b62f58ff1dc9" src="https://github.com/user-attachments/assets/8b3b6031-f9f6-46db-9e98-33329c49fcff" />
SERVER.PY


<img width="752" height="717" alt="541393781-acb3fd65-16b3-49d7-8f8f-52cf726a5687" src="https://github.com/user-attachments/assets/b6955a7e-d464-456e-a3fd-297fd00dc6c6" />

## RESULT:
The program is executed successfully
