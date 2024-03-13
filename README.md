# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
# CILENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
# SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
# CILENT
![307815408-0dea660d-c2dd-4af8-9419-464f8d4ca752](https://github.com/Sudharsanram/2c.ARP_RARP_PROTOCOLS/assets/119393980/17281f94-4515-4373-bc86-5f8ba44a5a0d)

# SERVER
![307815429-9e817ca1-6258-40c4-96eb-a77966f0a5e2](https://github.com/Sudharsanram/2c.ARP_RARP_PROTOCOLS/assets/119393980/ed67fd0d-f020-4f1a-aab5-5163998f826d)

## PROGRAM - RARP
# CILENT
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
   c.send(address[ip].encode())
 except KeyError:
   c.send("Not Found".encode())
```
# SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
# CILENT 
![307816609-dc4dd577-6dbb-4497-ba92-0f74603cfbed](https://github.com/Sudharsanram/2c.ARP_RARP_PROTOCOLS/assets/119393980/46b60e1c-1390-4dc2-8a7a-875e19def651)
# SERVER
![307816633-b3ff5889-3620-410f-a324-3328039e90c6](https://github.com/Sudharsanram/2c.ARP_RARP_PROTOCOLS/assets/119393980/1188cc99-ca0c-4445-b41a-067dd756ef5f)
## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
