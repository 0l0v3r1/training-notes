# About Python

## 3.0 Introduction

Nothing Special to mention until 3.9

***
***

# Pentester Scripting

## 3.9.1 Network Sockets

* Network Sockets are used in computer networks to exchange data (packets) between two endpoints (from source to destination)
* We need to import the `socket` module then get the address and the ip from the user
* **Example:** We are going to write a program that binds itself to a specific address and port and will listen for incoming TCP connection (a server)

```python
import socket

SRV_ADDR = input("Type the Server IP address: ")
SRV_PORT = int(input("Type the Server Port: "))

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind((SRV_ADDR, SRV_PORT))
s.listen(1)
print("Server Started! Waiting for connection...")
connection, address = s.accept()
print("Client Connected with address: ", address)
while 1:
    data = connection.recv(1024)
    if not data:
        break
    connection.sendall(b'--Message Received--\n')
    print(data.decode('utf-8'))
connection.close


```

## 3.9.1.1 Network Sockets - Exercise

* The task is to use the socket module to create a client that starts a connection to the python server and then sends a message.

* **My Code:**
```python
import socket

SRV_ADDR = input("Type the Server IP address: ")
SRV_PORT = int(input("Type the Server Port: "))

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.connect((SRV_ADDR, SRV_PORT))

while 1:
    print(str(s.recv(1024)))
    toSend = input()
    s.send(bytes(toSend, "utf-8"))

```

* **INE's Solution**
```python
import socket

SER_ADDR = input("Type the Server IP address: ")
SER_PORT = int(input("Type the Server Port: "))

my_sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
my_sock.connect((SER_ADDR, SER_PORT))
print("Connection established")

message = input("Message to send: ")
my_sock.sendall(message.encode())
my_sock.close()

```

## 3.9.2 Port Scanner

* The sample code for a simple port scanner provided by INE:

```python
import socket

target = input("Enter the target IP to scan: ")
portrange = input("Enter the port range to scan (Ex: 5-200): ")

lowport = int(portrange.split('-' [0]))
highport = int(portrange.split('-' [1]))

print("Scanning host", target, "from port", lowport, "to port", highport)

for port in range(lowport, highport):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    status = s.connect_ex((target, port))
    if(status == 0):
        print("*** Port", port, " is open")
    else:
        print("*** Port", port, " is Closed")
    s.close

```


## 3.9.2.1 Backdoor - Exercise

* **My Code:**

**Server:**

```python
import platform
import socket
import re
import uuid
import json
import psutil
import logging
import os


def getSystemInfo():
    try:
        info = {}
        info['platform'] = platform.system()
        info['platform-release'] = platform.release()
        info['platform-version'] = platform.version()
        info['architecture'] = platform.machine()
        info['hostname'] = socket.gethostname()
        info['ip-address'] = socket.gethostbyname(socket.gethostname())
        info['mac-address'] = ':'.join(re.findall('..', '%012x' % uuid.getnode()))
        info['processor'] = platform.processor()
        info['ram'] = str(round(psutil.virtual_memory().total / (1024.0 ** 3))) + " GB"
        return json.dumps(info)
    except Exception as e:
        logging.exception(e)


SRV_ADDR = "127.0.0.1"
SRV_PORT = int("3344")
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind((SRV_ADDR, SRV_PORT))
s.listen()
print("Server Started! Waiting for connection...")
connection, address = s.accept()
print("Client Connected with address: ", address)
messageInfo = str(json.loads(getSystemInfo()))
connection.send(messageInfo.encode())
message = connection.recv(1024)
directory = message.decode()
print(os.listdir(directory))
connection.close()

```

**Client:**

```python
import socket

# SRV_ADDR = input("Type the Server IP address: ")
# SRV_PORT = int(input("Type the Server Port: "))

SRV_ADDR = "127.0.0.1"
SRV_PORT = int("3344")

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.connect((SRV_ADDR, SRV_PORT))

data = s.recv(1024)
print("System Info:")

print(data.decode())

print("What Directory would you like to fetch? ")
directory = input()
s.send(directory.encode())
s.close()

```

## 3.9.3.1 HTTP Exersice

* Write a program that verifies if a specific resource exists:

```python
import http.client

host = input("Enter The IP address: ")
port = input("Enter The Port number (default=80): ")
url = input("Enter The URL: ")

if (port == ""):
    port = 80

try:
    connection = http.client.HTTPConnection(host, port)
    connection.request('GET', url)
    response = connection.getresponse()
    print("Server Response: ", response.status)
    connection.close
except ConnectionRefusedError:
    print("Connection Failed!")

```

## 3.9.3.2 Login Brute Force - Exercise

I didn't did it.. No enough info
Will do something similar in LABs

