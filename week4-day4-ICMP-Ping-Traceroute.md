# Day 4 — ICMP, Ping & Traceroute

---

# Warm-Up — Multiple Choice Review

Try these WITHOUT notes.

---

## 1. Which device primarily forwards traffic between different networks?

A) Switch

B) Router

C) Hub

D) Access Point

Answer: b

---

## 2. Which device primarily forwards traffic using MAC addresses?

A) Router

B) DNS Server

C) Switch

D) DHCP Server

Answer: c

---

## 3. What does DNS do?

A) Assigns IP addresses automatically

B) Translates domain names into IP addresses

C) Routes traffic

D) Stores MAC addresses

Answer: b

---

## 4. What does DHCP do?

A) Encrypts web traffic

B) Assigns IP addresses automatically

C) Resolves domain names

D) Routes packets

Answer: b

---

## 5. Which protocol is connection-oriented?

A) UDP

B) ICMP

C) TCP

D) DNS

Answer: c
---

## 6. Which protocol is generally faster because it does not retransmit lost packets?

A) TCP

B) UDP

C) HTTP

D) HTTPS

Answer: b

---

## 7. Which port is commonly used by HTTPS?

A) 22

B) 53

C) 80

D) 443

Answer: d

---

## 8. Which port is commonly used by SSH?

A) 20

B) 21

C) 22

D) 443

Answer: c

---

# Task 1 — ICMP

# ICMP
Internet Control Message Protocol

---

## Multiple Choice

### What is ICMP?

A) A protocol used for file transfers

B) A protocol used for network diagnostics and error reporting

C) A protocol used for web browsing

D) A protocol used for assigning IP addresses

Answer: b

---

### Which tool commonly uses ICMP?

A) chmod

B) FTP

C) ping

D) apt

Answer: c

---

## Short Answer

### What does ICMP stand for?

Internet Control Message Protocol

---

### What is ICMP used for?
The ICMP protocol is mainly used for sending network diagnostics and error messages between devices in layer 3. 


---

### Is ICMP a transport protocol like TCP or UDP?

A) Yes

B) No

Answer: b

---

# Echo Request & Echo Reply

## Multiple Choice

### Which ICMP message is sent first when using ping?

A) Echo Reply

B) Echo Request

C) SYN

D) ACK

Answer: b

---

### What message is returned if the destination responds?

A) Echo Reply

B) SYN-ACK

C) DNS Response

D) HTTP Response

Answer: a

---

## Fill In The Blanks

Step 1:

Your computer sends an Echo Request.

---

Step 2:

The destination responds with an Echo Reply.

---

## Short Answer

### What protocol does ping use?
The ping command used the ICMP protocol in particular. 

---

### Why is ICMP useful for network administrators?
ICMP is useful for network administrators because it provides error reporting and network diagnostics without transporting user data, which adds an extra level of security. 
Note: ICMP helps administrators troubleshoot connectivity problems, test reachability, identify routing issues, and diagnose network failures. (Graded)

---

# In Your Own Words

### Explain ICMP like you're teaching a beginner.
ICMP is a protocol used in the network layer of the OSI model that sends diagnostics and error messages between devices. This is the main protocol used in the ping command. 


---

# Task 2 — Ping & Traceroute

# Ping

---

## Practice Command

```bash
ping google.com
```

### What happened when you ran this command?
When I ran this command, it started to ping google contiuously, and I had to use ctrl + c to stop it. 

---

## Practice Command

```bash
ping 8.8.8.8
```

### What happened when you ran this command?
When I ran this command, it pinged the IP address 8.8.8.8 contiuosly, and I had to use ctrl + c to stop it. 

---

## Multiple Choice

### What does ping primarily test?

A) File permissions

B) Network connectivity

C) User accounts

D) DNS records only

Answer: b

---

## Short Answer

### Why might you ping an IP address instead of a domain name?
Some reasons to ping an IP address instead of a domain name is to bypass DNS resolution issues, isolate network connectivity problems, or test direct server reachability. 
Note: I am not too sure about this, but another reason might be that sometimes, you need to go to site that does not have a domain name (such as your network settings), and pinging the IP address for that site will allow you to test stuff if needed. I don't know if this is a valid reason though, so take it with a grain of salt. 
    Note: It is valid. 


---

# Traceroute

---

## Practice Command

```bash
traceroute google.com
```

### What happened when you ran this command?
When I ran this command, it showed me the path the request took in order to get to google.com. 

---

## Multiple Choice

### What does traceroute show?

A) Active users

B) Running processes

C) The path packets take to a destination

D) Open files

Answer: c

---

## Short Answer

### What information did traceroute display?
The traceroute command displayed the path my request took in order to get to the destition, which was google.com. 

---

### Why is traceroute useful?
Traceroute is useful because it maps the specific paths data packets take from a source to a destination, revealing how many hops (intermediate routers) there were along the way. 

---

# Ping vs Traceroute

## Multiple Choice

### Which tool is best for testing whether a destination is reachable?

A) Traceroute

B) Ping

Answer: b

---

### Which tool is best for seeing where a connection may be slowing down or failing?

A) Ping

B) Traceroute

Answer: b

---

## In Your Own Words

### What is the biggest difference between ping and traceroute?
The biggest difference between ping and traceroute is that ping tests to see whether a connection to a destination is possible, while traceroute shows the path a data packet takes in order to get to that specific destination. 


---

# Reflection

## Which command felt easier to understand?
I would say neither of them felt easier than the other, as while traceroute felt easy to understand, tracking how many routers the data packet went through to get to the destination, ping also felt very easy, so I would they are about the same. 

---

## Which concept was most confusing?
I would say the question of why it is useful to ping the IP address was a little difficult for me, as I didn't think about something like that at first, and it took me a little bit to understand why. 

---

## In one sentence, explain why ping and traceroute are useful.
Ping and traceroute are useful commands because they help test and troubleshoot network connectivity and DNS issues. 
Note: Ping and traceroute help troubleshoot network connectivity, routing paths, and DNS-related issues. (Graded)

---

