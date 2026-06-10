# Day 2 — Ports

# Warm-Up — Multiple Choice Review

Try these WITHOUT notes.

---

## 1. Which permission string represents `chmod 755`?

A) rwxrwxrwx

B) rwxr-xr-x

C) rw-r--r--

D) rwx------

Answer: b

---

## 2. Which command changes the owner of a file?

A) chmod

B) chown

C) groups

D) pwd

Answer: b

---

## 3. Which command shows the groups a user belongs to?

A) id

B) whoami

C) groups

D) ls

Answer: c

---

## 4. What does LAN stand for?

A) Local Area Network

B) Large Area Network

C) Logical Access Network

D) Linked Area Network

Answer: a

---

## 5. What does WAN stand for?

A) Wireless Area Network

B) Wide Area Network

C) Web Access Network

D) Wired Area Network

Answer: b

---

## 6. Which device primarily forwards traffic between different networks?

A) Switch

B) Router

C) Hub

D) Access Point

Answer: b

---

## 7. Which device primarily forwards traffic using MAC addresses?

A) Router

B) DNS Server

C) Switch

D) DHCP Server

Answer: c

---

## 8. Which type of IP address is assigned by your ISP and visible on the Internet?

A) Private IP

B) Loopback IP

C) Public IP

D) Local IP

Answer: c

---

## 9. Which private IP range is commonly used in home networks?

A) 8.8.8.8

B) 192.168.x.x

C) 127.0.0.1

D) 1.1.1.1

Answer: b

---

# Task 1 — What Are Ports?

# Ports

---

## Multiple Choice

### What is a port?

A) A physical connector on a computer

B) A logical number used to identify a network service

C) A type of IP address

D) A MAC address

Answer: b

---

### Which protocol layer commonly uses port numbers?

A) Physical Layer

B) Data Link Layer

C) Transport Layer

D) Network Layer

Answer: c

---

## Short Answer

### What is a port?
A port is a communication endpoint used to direct network traffic to specific processes and services on a device. 

---

### Why do computers need ports?
Computers need ports to serve as the essential bridges for connectivity, data transfer, and expandability, allowing the system to interact with external devices and services. 
Note: One computer can run many services simultaneously. Ports tell the computer "This packet belongs to THIS application.". (Graded)

---

### What problem do ports solve?
Ports solve the problem of directing network traffic to the correct application on a device that shares a single IP address. Without ports, computers wouldn't know which software process is appropiate for incoming data packets. 

---

# Service Identification

## Multiple Choice

### Which port is commonly used by HTTP?

A) 22

B) 53

C) 80

D) 443

Answer: c

---

### Which port is commonly used by HTTPS?

A) 80

B) 22

C) 53

D) 443

Answer: d

---

### Which port is commonly used by SSH?

A) 22

B) 80

C) 443

D) 21

Answer: a

---

### Which port is commonly used by DNS?

A) 20

B) 22

C) 53

D) 443

Answer: c

---

## Fill In The Blanks

FTP uses ports 20 and 21

SSH uses port 22

DNS uses port 53

HTTP uses port 80

HTTPS uses port 443

---

# Common Ports Reference

| Service | Port |
|-----------|-----------|
| FTP | 20/21 |
| SSH | 22 |
| DNS | 53 |
| HTTP | 80 |
| HTTPS | 443 |

---

# Questions

## Can multiple services use the same port at the same time?

A) Yes

B) No

Answer: no

---

## Why or why not?
Multiple services cannot use the same port at the same time because if they were to attempt to use the same port at the same time, the second application would not be able to, as it would error out. 

---

# In Your Own Words

### Explain ports like you're teaching a beginner.
A port is a physical endpoint on a computer that helps directs network traffic to applications and services on a device. They allow the device in question to interact with external devices, peripherals, and services. 

Note: A port is a numbered doorway that allows a computer to send incoming network traffic to the correct application or service. (Graded)

---

# Task 2 — Viewing Ports

# Practice Commands

---

## Command

```bash
netstat -tuln
    #This command lets you display a list of all active TCP and UDP listening sockets on your system. 
    -t
        #This flag lists all the TCP connections. 
    -u
        #This flag lists all the UDP connections. 
    -l
        #This flag lists only the listening sockets (which are services waiting for connections).
    -n
        #This flag lists the numeric addresses and ports. 
```

### What does this command show?
When I input this command on my vm, it listed all the active internet connections on my system (with all the flags of course) as well as the numeric addresses and ports for the connections. 

---

### What listening ports do you see?
I only see around 4 listening ports, but they are the first 4 ones listed. 

---

## Command

```bash
ss -tuln
    #This command lets you display socket statistics and detailed information about network connections. 
    -tuln
        #These flags are the same as the one above. 
```

### What does this command show?
When I input this command, it displayed detailed information regarding network connections, including if they are TCP or UDP, if they are listening ports, and their numeric addresses and ports. 

---

### What listening ports do you see?
When I look at what is displayed, it seems that only the TCP ports are listed as listening. 

---

# Understanding LISTEN

## Multiple Choice

### What does LISTEN mean?

A) The service is waiting for incoming connections

B) The service is currently downloading files

C) The service is disconnected

D) The service is forwarding packets

Answer: a

---

## Short Answer

### Why is LISTEN important?
LISTEN is important because it shows what services are waiting for a connection, allowing you to verify if a service is running and bound to port. It also helps with security auditing, as it allows adiministrators to monitor the system to see if any service poses a threat. 

---

# Practical Observation

## Did you see any listening ports on your VM?

A) Yes

B) No

Answer: a

---

### If yes, which ports?
It seems that all the TCP ports are listening ports, which might be because they are stuck in retransmission or something else may be happening. 
Note: They are not stuck in retransmission. It simply means a service is sitting there waiting for someone to connect. (Graded)

---

# In Your Own Words

### What does a listening port mean?
A listening port is a service that is waiting for incoming connections. 

---

# Reflection

## Which port was easiest to remember?
I would say port 22 is the easiest to remember, because ssh is something that I am going to be using a lot in my field I assume, so that's why that one was a little easier to remember than others. In general, I need to be able to memorize the important ports in order to fully excel in this concept. 

---

## Which concept was most confusing?
I would say the most confusing thing for me was understanding that these aren't physical ports, but rather logical addresses. I didn't realize that at first, and is something I need to familiarize myself with. 

---

## In one sentence, explain why ports are important.
Ports are important because they tell the computer what data belongs to what application/service, ensuring that each packet goes to the correct place. 


---