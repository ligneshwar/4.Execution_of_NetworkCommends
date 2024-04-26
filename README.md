# 4.Execution of Network Commands
## AIM :
Use of Network commands in Real Time environment
## Software :
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>
## Program
### Ping command
### Client.py
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### Server.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
## CLIENT:
![Screenshot 2024-04-26 153544](https://github.com/ligneshwar/4.Execution_of_NetworkCommends/assets/149365037/cced15e6-64fb-4d29-b4f0-a29e2c17bed7)

### SERVER:
![Screenshot 2024-04-26 153652](https://github.com/ligneshwar/4.Execution_of_NetworkCommends/assets/149365037/9e5c09ec-133a-458c-8a07-00c40298a11b)

### TRACEROUTE COMMAND:
![Screenshot 2024-04-26 153652](https://github.com/ligneshwar/4.Execution_of_NetworkCommends/assets/149365037/50e43a8a-421c-4e5c-b214-ff56f70f797f)

## Result
Thus Execution of Network commands Performed and program runned successfully. 
