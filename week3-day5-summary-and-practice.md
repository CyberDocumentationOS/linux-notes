# Active Learning Day 5 — Networking Review & Mini Project

---

# Warm-Up — Multiple Choice Review Quiz

Try these WITHOUT notes.

---

## 1. What is an IP address?

A) A unique hardware address assigned to a network card

B) A logical address used to identify a device on a network

C) A type of router

D) A subnet mask

Answer: b

---

## 2. What is a MAC address?

A) A logical address assigned by DHCP

B) A website address

C) A unique hardware address assigned to a network interface

D) A DNS record

Answer: c
---

## 3. Which device primarily forwards traffic between different networks?

A) Switch

B) Hub

C) Router

D) Access Point

Answer: c

---

## 4. Which device primarily forwards traffic inside a LAN using MAC addresses?

A) Router

B) Switch

C) DNS Server

D) DHCP Server

Answer: b

---

## 5. What does DNS do?

A) Assigns IP addresses automatically

B) Routes traffic

C) Translates domain names into IP addresses

D) Stores MAC addresses

Answer: c

---

## 6. What does DHCP do?

A) Assigns IP addresses automatically

B) Translates domain names

C) Stores MAC addresses

D) Routes traffic

Answer: a

---

## 7. What does a subnet mask help determine?

A) Which part of an IP address is the network and which part is the host

B) Which MAC address belongs to a device

C) Which DNS server to use

D) Which website to visit

Answer: a

---

## 8. What is a default gateway?

A) A backup DNS server

B) The device used to reach other networks

C) A subnet mask

D) A MAC address

Answer: b

---

## 9. Which command displays network interfaces and IP addresses?

A) ip route

B) ip addr

C) hostname -I

D) dig

Answer: b

---

## 10. Which command displays routing information?

A) ip route

B) ip link

C) nslookup

D) ping

Answer:a

---

# Task 1 — Networking Review Lab

# Command Review

---

## Command

```bash
ip addr
```

### What does this command show?
This commands displays the network interfaces and IP addresses associated with the linux system. 


---

### Why is it useful?
It is useful because it can help identify the status of the network devices associated with your system and help troubleshoot them if needed. 

---

## Command

```bash
ip link
```

### What does this command show?
This command lets you display layer 2 network devices associated with your linux system, allowing you to view the MAC address in the process. 


---

### Why is it useful?
This is useful because it allows you to view the status of the layer 2 devices and help you manage/troubleshoot them if needed. 

---

## Command

```bash
ip route
    #This command lets you display, add, delete, and modify entries in the system's IP routing table. 
```

### What does this command show?
This command allows you to view and manage the entires in the system's IP routing table. 


---

### Why is it useful?
This command is useful because it can help you manage and troubleshoot IP addresses on your linux system. 

---

## Command

```bash
hostname -I
```

### What does this command show?
This command lets you display all the network addresses assigned to the host linux system across all network interfaces. 

---

### Why is it useful?
This command is useful because it lets you view both your IPv4 and IPv6 address easily, while also allowing you to see any other assigned addresses to your system. 


---

## Command

```bash
nslookup google.com
```

### What does this command show?
This command lets you query DNS servers for the domain name and IP address mappings of the specified entry (in this case, google.com). 


---

### Why is it useful?
This is useful because it lets you see the domain name and IP address information for any domain you desire. 

---

# Command Comparison

## Which command would you use to find your IP address?
ip addr (or hostname -I)

---

## Which command would you use to find your MAC address?
ip link


---

## Which command would you use to find your default gateway?
ip route


---

## Which command would you use to test DNS resolution?
nslookup

---

# Networking Review

## IP Address

### In your own words, what is an IP address?
An IP address is a numerical label that is assigned to every device on a network that helps identify devices on a network.
Note: used to identify and locate devices on a network (Graded)

---

## MAC Address

### In your own words, what is a MAC address?
A MAC address is a label is assigned to a device's NIC that is used as an identifier in layer 2 operations.  
Note: forwards traffic using MAC addresses inside a LAN (Graded)

---

## Router

### In your own words, what does a router do?
A router is a networking device that uses IP addresses to move traffic from one network to another.


---

## Switch

### In your own words, what does a switch do?
A switch is a networking device that connects devices to one another, such as computers and servers. 

---

## DNS

### In your own words, what does DNS do?
DNS is a system that translates domain names into machine-readable IP addresses. This allows us to use the internet without having to memorize a bunch of IP addresses to access websites we want.

---

## DHCP

### In your own words, what does DHCP do?
DHCP is a service that automatically assigns IP addresses (and technically network configuration parameters) to devices on a network, eliminating the need for humans to do it. 

---

## Subnet Mask

### In your own words, what does a subnet mask help determine?
A subnet mask is meant to help determine the host portion of the IP address from the network portion of the IP address. 
Note: separates the network portion and host portion (Graded)

---

## Default Gateway

### In your own words, what is a default gateway?
A default gateway is a device that acts as an access point for devices on a local network to communicate with devices on an external network. 

---

# Task 2 — Final Network Diagram

Create:

![Diagram](home-network-diagram.png)



Include:

- Internet
- ISP Connection
- Router
- Switch (if applicable)
- Access Point (if applicable)
- Main Computer
- Virtual Machine
- Other Devices
- IP Addresses (optional)
- MAC Addresses (optional)

---

## Reflection Questions

### What part of your network was easiest to identify?
The easiest part was the ISP, as all I have to do is identify the ISP we use and that was it. 

---

### What part was hardest to identify?
The hardest part to identify would be the switch, access point, and DHCP, as they are all technically in the router itself. 

---

### Did drawing the network help you understand it better?
Drawing the diagram made me more involved in my family's home network than before, as now I see a lot of the smaller details most people don't pay notice to. 

---


# Week 3 Reflection

## IP Addresses

### What did you learn?
I learned what IP addresses are, how they used, and the technical details surrounding them (like default gateways).

---

## MAC Addresses

### What did you learn?
I learned what MAC addresses are, what MAC means (Media Access Control), and how layer 2 devices use them for their operations. 


---

## Routers

### What did you learn?
I learned what routers are, how they use IP addresses to help forward packets, and what the process of routing is. 


---

## Switches

### What did you learn?
I learned what switches are, how they use MAC addresses to help forward frames, and the differences between switches and hubs.  

---

## DNS

### What did you learn?
I learned what DNS is, what its name stands for (Domain Name System), and how to query DNS information on linux. 

---

## DHCP

### What did you learn?
I learned what DHCP is, hidden details some people forget about it, and why it is used in bigger networks. 

---

# Self-Evaluation

## What topic felt easiest?
DHCP felt the easiest to me, as it was something that seemed simple compared to something like the OSI model. 


---

## What topic felt hardest?
I would say the very specific details about switching and routing had me confused, as they were very in depth for something that is mainly conceptual.

---

## What topic do you want to learn more about?
I think the main thing I want to learn more about is applying these concepts into practice, like setting up mock networks and DHCP. 


---

## Confidence Rating

Rate your networking confidence after Week 3:

Answer: 3/10

## Why
While it is true that I learned a lot about networking this week, there is still a lot of things I need to learn before I can say I am confident in my skills. But with that said, I am a little more comfortable when it comes to the conceptual areas than I was before, so that is good at least. I am hoping to get better at networking to where I no longer need to frequent notes for questions, which time will help alleviate. 
