# Day 5 — Nmap Basics & VM Scan

## Warm-Up — Multiple Choice Review

Try these WITHOUT notes.

---

### 1. Which protocol is connection-oriented?

A) UDP

B) ICMP

C) TCP

D) DNS

Answer: c

---

### 2. Which protocol is generally faster because it does not retransmit lost packets?

A) TCP

B) UDP

C) HTTP

D) HTTPS

Answer: b

---

### 3. Which port is commonly used by HTTPS?

A) 22

B) 53

C) 80

D) 443

Answer: d

---

### 4. Which port is commonly used by SSH?

A) 20

B) 21

C) 22

D) 443

Answer: c

---

### 5. What does DNS do?

A) Assign IP addresses

B) Translate domain names into IP addresses

C) Route packets

D) Encrypt web traffic

Answer: b

---

### 6. What does DHCP do?

A) Resolve domain names

B) Assign IP addresses automatically

C) Route traffic

D) Encrypt traffic

Answer: b

---

### 7. Which command shows the path packets take to a destination?

A) ping

B) traceroute

C) netstat

D) ip addr

Answer: b

---

### 8. What protocol does ping primarily use?

A) TCP

B) UDP

C) ICMP

D) HTTP

Answer: c

---

# Task 1 — Nmap Basics

# Nmap

Network Mapper

---

## Multiple Choice

### What is Nmap?

A) A Linux package manager

B) A network scanning and discovery tool

C) A file transfer protocol

D) A DNS server

Answer: b

---

### Why is Nmap commonly used?

A) To edit files

B) To manage user accounts

C) To discover hosts and services on a network

D) To create virtual machines

Answer: c

---

## Short Answer

### What does Nmap stand for?
Nmap stands for Network Mapper. 


### What is Nmap used for?
Nmap is used for network discorvery and security auditing mainly. 


### Why is Nmap useful for cybersecurity?
Nmap is useful for cybersecurity because it provides comprehensive network visibillity, allowing you to discover active hosts, map network topology, and identify open ports and running services on the system. 


# Basic Scans

## Practice Command

```bash
nmap 127.0.0.1
    #This command performs a port scan against the localhost (loopback) interface, allowing you to identify services and ports that are bound specifically to the local machine. 
```

### What does this command do?
When this command was input, it performed a port scan on the localhost (loopback) interface, displaying services and ports that are bound to the localhost. 


### What open ports were found?
When I looked to see what ports were found, it said that 999 TCP ports were closed, and that only one port was open, which was 631 (a TCP port). 


### What services appear to be running?
When I looked to see what was displayed, there was only one service listed, which was IPP. 
Note: This was the only service mentioned in the output, so I might be missing something, but it seems like that is the only thing that is concrete. 


## Practice Command

```bash
nmap 10.0.2.15
    #This command port scan on the IP interface you choose (10.0.2.15), allowing you to identify services and ports that are bound to that interface. 
```

### What does this command do?
When I input this command, it performed a port scan of my ubuntu vm, identifying the services and ports bound to the VM. 


### What open ports were found?
When I looked at the results, it noted that there were 1000 closed tcp ports with 0 open ports. 
Note: At the end of where it said 1000 closed tcp ports, it said "(conn-refused)", which I'm guessing means connection refused (it did the same thing last time too), but I am not sure what that means.  
    Note: Conn-refused means that the host is reachable and the port exists, but no service is accepting connections there at the moment. (Graded)

### What services appear to be running?
When I looked at the results, it seemed that there were 0 services running at the time of the port scan. 
Note: No network services were listening on the scanned ports. (Graded)

# Understanding Results

## Multiple Choice

### What is an open port?

A) A port currently accepting connections

B) A broken network connection

C) A disabled service

D) A closed application

Answer: a

---

### What is a closed port?

A) A port actively accepting connections

B) A port that is not accepting connections

C) A port with malware

D) A DNS record

Answer: b

---

## Short Answer

### Why might an attacker be interested in open ports?
Attackers are interested in open ports due to the fact that they are entry points to the network, which can allow them to probe the network, identify services, and exploit vulnerabilities. 


### Why might a defender be interested in open ports?
Defenders are interested in open ports because it leads them to detecting threats like unauthorized services, misconfigurations, and vulnerable software versions that can lead to data exfiltration. 


# In Your Own Words

### Explain Nmap like you're teaching a beginner.
Nmap is a tool that is used for network scanning and discovery, along with being used for security monitoring. It helps identify running services and ports on a system, and can be used as a catalyst for cybersecurity related events. 


# Task 2 — Scan Your VM

# VM Scan Report

## VM Information

### IP Address Scanned

```text
10.0.2.15

```

---

### Command Used

```bash
nmap 10.0.2.15
nmap -p 22,80,443 10.0.2.15
    #This command does a port scan of only the requested ports (in this case, 22,80,443).
```

---

# Results

## Open Ports Found

```text
Broad scan:
    0 open ports
Specific scan:
    0 open ports
```

---

## Closed Ports Found

```text
Broad scan:
    1000 closed tcp ports
Specific scan:
    22/tcp Closed
    80/tcp Closed
    443/tcp Closed
```

---

## Services Detected

```text
Broad scan:
    0 services detected
Specific scan:
    None
    Ports scanned: 
        22/tcp ssh
        80/tcp http
        443/tcp https
        
    All were closed. 
```

---

# Observations

### Did anything surprise you?
No, I kind of expected there to be 0 open ports like before, as nothing really changed from last time. 


### Were there fewer open ports than expected?
No, but that was because I expected 0 open ports, and that expectation was met. 


### Why might minimizing open ports improve security?
Open ports serve as entry points to the network, which can result in attacker breaching into the network. By closing those open ports, it eliminates places they can enter, eventually locking them out of the network entirely. 


# Screenshots

Insert screenshots of:

![Nmap command and results](command-and-results-nmap.png)

---

# What I Learned

### What is one thing you learned about Nmap?
One thing I learned about nmap is that it is very integral to cybersecurity operations, as it is a commonly used tool when it comes to security auditing on a network. 


### What is one thing you learned about your VM?
One thing I learned about my vm is the fact that it really doesn't run any services unless I actively input it, which was surprising to me. 

### Why is port scanning important in cybersecurity?
Port scanning is important to cybersecurity because ports serve as entryways to the network, so being able to scan all ports to see which ones are open, have services running, and have unauthorized activity going on really helps defenders prevent attacks from happening. 


# End-of-Week Reflection

## Confidence Level (1–10)

Networking Fundamentals II:

4 / 10

---

## Which topic felt easiest this week?

A) TCP vs UDP

B) Ports

C) HTTP/HTTPS

D) SSH/FTP

E) ICMP/Ping/Traceroute

Answer: a

---

## Which topic felt hardest this week?

A) TCP vs UDP

B) Ports

C) HTTP/HTTPS

D) SSH/FTP

E) ICMP/Ping/Traceroute

Answer: b

---

## In one sentence, what was the biggest thing you learned this week?
The biggest thing I learned this week were network ports, as they are a very crucial part of networking. Another big thing I learned was nmap, as it is something that is going to be important in my career moving forward. 

