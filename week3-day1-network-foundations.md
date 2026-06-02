# Active Learning Day 1 — Network Foundations

# Warm-Up — Multiple Choice Quiz

Answer WITHOUT notes.

---

## 1. What is an IP address?

A) A physical address burned into a network card  
B) An identifier used to locate a device on a network  
C) A type of router  
D) A DNS record

Answer: b

---

## 2. What is a MAC address?

A) A website address  
B) A temporary IP address  
C) A unique hardware address assigned to a network interface  
D) A subnet mask

Answer: c

---

## 3. What device primarily connects different networks together?

A) Switch  
B) DNS Server  
C) Router  
D) DHCP Server

Answer: a (Correct answer is c)

---

## 4. What does a switch primarily use to forward traffic?

A) IP addresses  
B) Domain names  
C) MAC addresses  
D) Subnet masks

Answer: a (Correct answer is C)

---

## 5. What does DNS do?

A) Assigns IP addresses automatically  
B) Translates domain names into IP addresses  
C) Encrypts network traffic  
D) Connects networks together

Answer: c (Correct answer is B)

---

## 6. What does DHCP do?

A) Resolves domain names  
B) Assigns IP addresses automatically  
C) Stores MAC addresses  
D) Routes traffic

Answer: b

---

# Task 1 — What Is a Network?

# Network

## What is a network?
A network is a collection of interconnected devices that are meant communicate with each other to share information between one another. 
A network's main goal is to essentially send information from one device to another, whether that be from a cabled connection or a wireless one. 
For this to work, the sender and reciever must understand eachother. The way they communicate with eachother are protocals, which is a set of instructions that tell the sender or reciever how to handle the information. Usually, several protocals are used in tandem to achieve a task.

---

# LAN

## What does LAN stand for?
Local Area Network
_____________________________________________________________

---

## What is a LAN?
A local area network (LAN) is a collection of devices connected together in one physical location, such as an office building or house. 
A LAN can be small or large, be that a home network or an enterprise network.


---

## Examples of a LAN

- SOHO (Small Office Home Office)
- Office Building 
- School Computer Lab

---

# WAN

## What does WAN stand for?
Wide Area Network
_____________________________________________________________

---

## What is a WAN?
A wide area network (WAN) is a collection of LANs/networks that communicate with one another. Think of it as a network of networks. 
Note: A WAN connects networks over large geographic distances. (Graded)
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## How is a WAN different from a LAN?
A LAN is a collection of devices in one physical location that communicate with each other, while a WAN is a collection of LANs or networks that communicate with each other over a vast distance.
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# Internet

## What is the Internet?
The internet is a global system of interconnected networks that uses the internet protocol suite (TCP/IP) to communicate between devices over vast distances.
Note: The Internet is a global network of interconnected networks. (Graded)
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Why is the Internet considered a network of networks?
The internet is consider a network of networks because it is not a single centralized thing, but a massive global infrastructure composed of thousands of interconnected smaller networks, including LANs, WANs, and Internet Service Provider (ISP) networks. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# Network Devices

## What is a network device?
A network device is a physical appliance that facilitates communication and interaction between devices on a network. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Common Network Devices

### Router

What does a router do?
A router is a networking device that connects multiple networks and data packets between them using ip address. Essentially, they forward data packets between networks. 
Note: A router connects different networks and forwards data packets between them using IP addresses.
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

### Switch

What does a switch do?
A switch connects devices within a local are network (LAN) and directs data traffic within that network. It uses MAC addressess to identify the specific devices so that the data packets only get fowarded to their intended recipients.
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

### Access Point

What does an access point do?
An access point allows wireless devices, such as tablets, laptops, and smartphones to connect to a wired network using Wi-Fi. The access point receives data from a wired network via an Ethernet cable and broadcasts it as a wireless signal, allowing wireless devices to connect. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# How Data Moves Between Devices

## Explain in simple terms how data travels from one device to another.
Data travels between devices by: 
1. Broken down into small packets, each contain a portion of original data along with the source and destination IP addresses and sequence numbers.
2. Packets are transmitted physically through mediums such as cables, optical fibers, or wireless signals, where digital data is converted into electrical, optical, or radio wave signals.
3. Routers and switches then direct these packets across the network by consulting routing tables to determine the best path. 
Note: Switches and routers direct packets across the network. Switches use MAC addresses to forward traffic within a network, while routers use routing tables and IP addresses to move traffic between networks.
4. Packets may be out of order, so sequence numbers are used to reassemble them into the original data form. 
Note: Data travels between devices by being broken into small packets of data. These packets are sent across the network through cables or wireless signals. Switches and routers help direct the packets to their destination. Once all the packets arrive, they are reassembled into the original data. (Graded)
---

# Task 2 — IP Addresses

# IP Address
Internet Protocol Address
## What is an IP address?
And IP address is a numerical label assigned to every device connected to a network that uses the inter protocol for communication.
Note: An IP address is a unique numerical identifier assigned to a device on a network. (Graded)
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Why does every device need an IP address?
Every device needs an IP address as they are unique digital identifiers and location labels, as they are essential for the internets's functionality, as it allows communication by directing data between devices, making sure it reaches the desired destination. Without an IP address, devices cannot send and recieve data packets, as there is no way to direct the information.

_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# IPv4

## What does IPv4 stand for?
Internet Protocol version 4.
_____________________________________________________________

---

## Example IPv4 Address
255.255.255.0
Note: 192.168.1.100 is a better example, as above is usually subnet mask. (Graded)
_____________________________________________________________

---

## How many numbers are in an IPv4 address?
There are 4 numbers in an IPv4 address, seperated by a ., and each number can only go as high as 255. 
_____________________________________________________________

---

# Public IP Address

## What is a public IP address?
A public IP address is a globally unique, internet-facing indentifier assigned to a network by an ISP, serving as the primary gateway for a home or business network.
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Who usually assigns a public IP address?
The internet service provider assigns the public IP addresses to the network router, not to individual devices. 
_____________________________________________________________

_____________________________________________________________

---

# Private IP Address

## What is a private IP address?
A private IP address is a unique identifier assigned to devices within a local network to allow interal communication. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Examples of Private IP Ranges

- Class A: 10.0.0.0 to 10.255.255.255
    Has 8 network bits and 24 host bits.
- Class B: 172.16.0.0 to 172.31.255.255
    Has 16 network bits and 16 host bits.
- Class C: 192.168.0.0 to 192.168.255.255
    Has 24 network bits and 8 host bits.
Note: I took these from a cisco learning website, so I am still confused on this right now. I would like to expand on this in the future and learn what these mean in more detail. 

---

# Loopback Address

## What is the loopback address?
A loopback address is a special IP address used by a network device to send data to itself. 
_____________________________________________________________

---

## What is it used for?
A loopback address allows for internal communication with the network device itself without the traffic leaving the local machine or passing through other physical network interfaces. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Why is 127.0.0.1 important?
This IP address is important because it is the most commonly used loopback address, and is often referred to as the localhost. This address is use primarily for testing network software, and developing loval services without external interference. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# Practice Commands

## Command

```bash
ip addr
    #When input, this command lets you display all network interfaces and their states, MAC addresses, IPv4, and IPv6 addresses. 
```

### What does this command do?
When I input this command, it showed me all the network interfaces connected to my system.
Note: Most of this was pretty foreign to me, so I will have to learn more about it in the future. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

## Command

```bash
hostname -I
    #When this command is input, it displays all network addresses assigned to the host across all configured network interfaces. 
```

### What does this command do?
When I input this command, is displayed the IPv4 address and IPv6 address of my system. 
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# Questions

## What is your Linux VM IP Address?
It was 10.0.2.15
_____________________________________________________________

---

## What is 127.0.0.1?
This specific ip address is the loopback address that is commonly used for the localhost device. It is used for internal communication and other procedures associated with that.
_____________________________________________________________

_____________________________________________________________

_____________________________________________________________

---

# Task 3 — Home Network Diagram

Draw a rough diagram of your network.

Example:

Internet
|
Router
|
PC
|
VirtualBox VM

Your Diagram:

Internet (ISP provider: Visuo)
|
Asus AX5400 Router
    Note: This not only acts as the router, but as a switch (it has an internal switch) and an access point, so it covers all 3 essentially. 
|
Extenders (Repeater)
    Used for dead spots in house.
|
Msi GF63 Laptop
|
VirtualBox Network Adapter
|
Ubuntu VM


---

# End of Day Reflection

## What concept was easiest today?
The LAN and WAN concpets were a lot easier than I thought they were going to be, which is a good thing in the long run. 
_____________________________________________________________

_____________________________________________________________

---

## What concept was most confusing?
I would say the private IP ranges were challenging to understand, as it was genuinely confusing to me about what network bits and host bits actually mean, but time will help me solve those problems.
_____________________________________________________________

_____________________________________________________________

---

## What do you want to learn more about?
I would like to learn more about applying these concepts in a practical manner on not only linux systems, but Windows and cisco systems as well, as it would be interesting to see how these concepts would be put into practice. 
_____________________________________________________________

_____________________________________________________________

---

## Confidence Level (1–10)
2/10
Why:
I am pretty new to these concepts as of right now, and I need to learn more about conceptual networking before I can say I am higher than a 2/10. With that said, time will help alieviate some of these concerns.
__________