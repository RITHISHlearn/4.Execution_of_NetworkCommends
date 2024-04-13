# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
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

## PROGRAM

## PING COMMAND

## CLIENT:

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

## SERVER

import socket 

s=socket.socket() 

s.connect(('localhost',8000)) 

while True: 

    ip=input("Enter the website you want to ping ") 
    
    s.send(ip.encode()) 
    
    print(s.recv(1024).decode())

    
## TRANCEROUTE COMMAND

from scapy.all import* 

target = ["www.google.com"] 

result, unans = traceroute(target,maxttl=32) 

print(result,unans) 

## Output

## PING COMMAND

## CLIENT

![Screenshot 2024-04-13 232225](https://github.com/RITHISHlearn/4.Execution_of_NetworkCommends/assets/145446645/7b538b93-7bf2-4435-9e8f-b5cfc993a3fd)

## SERVER

![Screenshot 2024-04-13 232240](https://github.com/RITHISHlearn/4.Execution_of_NetworkCommends/assets/145446645/8d19e1ea-b7e2-42cd-a92a-ee32f81baad6)


## TRANCEROUTE COMMAND

![Screenshot 2024-04-13 232256](https://github.com/RITHISHlearn/4.Execution_of_NetworkCommends/assets/145446645/6977f7da-09bf-4024-96f3-b1628b60faeb)


## Result
Thus Execution of Network commands Performed 
