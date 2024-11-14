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
### Server :
```
import socket
HOST = "127.0.0.1"
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```

### Client :
```
import socket
HOST = "127.0.0.1" 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```

## OUTPUT:
### server :
![Screenshot (191)](https://github.com/user-attachments/assets/d62ba3ab-f615-4fc0-8020-a565ce013a11)


### Client :
![image](https://github.com/user-attachments/assets/65719781-44ea-439c-afb2-c63ceffa2b48)


## RESULT:
The program is executed successfully
