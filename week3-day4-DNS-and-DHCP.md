# Active Learning Day 4 — DNS & DHCP

---

# Warm-Up — Multiple Choice Quiz

Try these WITHOUT notes.

---

## 1. Which Linux command is commonly used to display network interface information?

A) ls -l  
B) chmod  
C) ip addr  
D) mkdir

Answer: c
---

## 2. Which command can display your system's IP address(es)?

A) hostname -I  
B) pwd  
C) rm  
D) touch

Answer: a

---

## 3. Which command is used to test network connectivity?

A) grep  
B) ping  
C) chmod  
D) mv

Answer: b

---

## 4. Which command shows the path packets take to a destination?

A) traceroute  
B) chown  
C) top  
D) sudo

Answer: a

---

## 5. Which command can query DNS information?

A) dig  
B) mkdir  
C) cat  
D) whoami

Answer: a

---

## 6. Which command can show the routing table?

A) ip route  
B) ls  
C) cp  
D) groups

Answer: a

---

## 7. What service automatically assigns IP addresses to devices?

A) DNS  
B) DHCP  
C) SSH  
D) HTTP

Answer: b

---

## 8. What service translates domain names into IP addresses?

A) DHCP  
B) DNS  
C) FTP  
D) TCP

Answer: b

---

# Task 1 — DNS

# DNS
Domain Name System

## Multiple Choice

### What does DNS do?

A) Assigns IP addresses automatically

B) Translates domain names into IP addresses

C) Moves traffic between networks

D) Stores MAC addresses

Answer: b

---

## Short Answer

### What does DNS stand for?
Domain Name System
_____________________________________________________________

---

### Why does DNS exist?
DNS exists to translate the human-friendly domain names into IP addresses that devices can use to identify and locate each other on the internet. 


---

### What problem does DNS solve?
DNS solves the problem of mapping human readable domain names to machine readable IP addresses, allowing humans to navigate the internet without having to memorize a bunch of ip addresses to go to certain websites.


---

# Domain Names

## Multiple Choice

### Which is easier for humans to remember?

A) 142.250.190.78

B) google.com

Answer: b

---

## Short Answer

### What is a domain name?
A domain name is a human readable address used to access websites on the internet. 

---

### Give three examples of domain names.

- youtube.com
- google.com
- bbc.co.uk

---

# DNS Resolution

## What happens when you type a website into a browser?

1. Browser looks up IP address for the domain.

2. Browser initiates TCP connection with the server.

3. Browser sends the HTTP request to the server. 

4. Server processes the request and sends back a response.

---

# Practice Commands

## Command

```bash
nslookup google.com
    #This command allows you to query DNS servers to obtain the domain name or IP address mappings for the specified entry. This command is also used to troubleshoot DNS-related issues. 
```

### What does this command do?
When I input this command, it gave me domain name, IP address, and other DNS information for google.com.

---

## Optional Command

```bash
dig google.com
    #This command allows you to perform DNS lookups and interrogate DNS name servers for the specified entry. 
```

### What does this command do?
When I input this command, it gave me a bunch of DNS information regarding google.com. 


---

# Questions

## Why don't we memorize IP addresses?
We don't memorize IP addresses because it is too complicated for us to remember all of the ones that are necessary. Everyone has a set of websites they go to, remembering the specific IP addresses of all of them is just too much. 
Note: IP addresses can change. (Graded)

---

## What does DNS translate?
DNS translates the human readable domain names into IP address that machines can read more easily. 


---

# In Your Own Words

### Explain DNS like you're teaching a beginner.
DNS is a service that allows use to use simple domain names like google.com to travel the internet. It achieves this by translating the human readable names into IP addresses, allowing for the devices necessary to achieve the desired result. Without DNS, we would have to memorize every IP address for the websites we visit, which is too much to handle. 

---

# Task 2 — DHCP

# DHCP
Dynamic Host Configuration Protocol

## Multiple Choice

### What does DHCP do?

A) Translates domain names

B) Assigns IP addresses automatically

C) Routes traffic

D) Stores MAC addresses

Answer: b

---

## Short Answer

### What does DHCP stand for?
Dynamic Host Configuration Protocol
_____________________________________________________________

---

### Why does DHCP exist?
DHCP exists to automate the assignment of IP addresses and the network configuration process for devices on a network. 


---

### What problem does DHCP solve?
DHCP solves the problem of manually configuring IP addresses on every device on a network, which is not only impractical, but has cause for errors as the network grows. DHCP eliminates this concern by automating the process, getting rid of human error and allowing for network growth at a reasonable scale. 


---

# Automatic IP Assignment

## Multiple Choice

### Without DHCP, what would usually happen?

A) Devices automatically choose correct addresses

B) Every device would need manual configuration

C) DNS stops working

D) Routers stop forwarding traffic

Answer: b

---

## Short Answer

### What information can DHCP provide besides an IP address?
DHCP provides other essential network configuration parameters along side IP addresses, like subnet masks, default gateway, and DNS server addressing. 


---

# DHCP Leases

## What is a DHCP lease?
A DCHP lease is a temporary agreement between a client device and a DHCP server that allows a device to use a specific IP address for a specified amount of time. 


---

## Why are leases useful?
DHCP leases are useful because they allow for efficient automated management of IP address pools, which prevent conflicts on the network.

---

# Questions

## What happens without DHCP?
Without DHCP, the devices on a network are not assigned IP addresses are any network parameters, requiring them to be set up manually. This is a time consuming process, and can cause IP conflicts and erorrs if they are set up incorrectly.  


---

## Why is DHCP important on large networks?
DHCP is important on large networks because setting everything up manually is not feasible to do due to the size of the network and how they evolve and grow over time. DHCP allows for these networks to automatically handle these issues, and allow for reasonable growth of networks. 


---

# In Your Own Words

### Explain DHCP like you're teaching a beginner.
DHCP is a system that automatically assigns IP addresses and network configuration parameters on network devices, allowing networks to configured properly (avoiding human error) and allowing them to have reasonable growth with ease. 
Note: DHCP allows devices to automatically receive the settings needed to communicate on a network. (Graded)
---

# DNS vs DHCP

## Multiple Choice

### Which service translates names into IP addresses?

A) DNS

B) DHCP

Answer: a

---

### Which service assigns IP addresses?

A) DNS

B) DHCP

Answer: b

---

# Quick Comparison

## DNS

Purpose:
To translate domain names into IP addresses. 
_____________________________________________________________

---

## DHCP

Purpose:
To assign IP addresses to devices on a network automatically. 
_____________________________________________________________

---

## Biggest Difference
DNS is meant for using the internet in an easy, human-friendly way. DHCP is meant to automatically assign IP addresses to devices on a network, allowing an easier time setting up a network. 


---

# End-of-Day Reflection

## What concept felt easiest today?
For me, the basic definition of DHCP felt the easiest to me, which is because I have expierence with it from my CCNA courses I took in college. I think because of that (and the fact that is a fairly straight forward), I was able to understand the concept easier than others. 


---

## What concept was most confusing?
I would say the most confusing concept was explaining the process of DNS, as there are a good amount of steps involved in the process, that make it a little difficult to commit to memory. 

---

## In your own words, explain the difference between DNS and DHCP.
DNS is a service that is meant to make traveling the internet easier, while DHCP is meant to make setting up a network easier. 


---