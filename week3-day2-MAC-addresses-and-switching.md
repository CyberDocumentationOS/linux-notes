# Active Learning Day 2 — MAC Addresses & Switching

---

# Warm-Up — Multiple Choice Quiz

Try these WITHOUT notes.

---

## 1. What is an IP address?

A) A hardware address assigned to a network card  
B) A logical address used to identify a device on a network  
C) A type of switch  
D) A wireless signal

Answer: b

---

## 2. What is a MAC address?

A) A logical address assigned by DHCP  
B) A website address  
C) A unique hardware address assigned to a network interface  
D) A subnet mask

Answer: c

---

## 3. Which device primarily connects different networks together?

A) Switch  
B) Router  
C) Hub  
D) Access Point

Answer: a (Correct answer b)

---

## 4. What information does a switch primarily use to forward traffic?

A) Domain names  
B) IP addresses  
C) MAC addresses  
D) Port numbers

Answer: c

---

## 5. Which OSI layer are MAC addresses associated with?

A) Layer 1 — Physical  
B) Layer 2 — Data Link  
C) Layer 3 — Network  
D) Layer 7 — Application

Answer: b

---

## 6. Which device is smarter than a hub because it forwards traffic only where needed?

A) Router  
B) Modem  
C) Switch  
D) DNS Server

Answer: a (correct answer c)

---

# Quick Recall

With notes:

IP Address = Unique numerical identifier each device on a network has.

MAC Address = Unique hardware address assigned to a network interface.

Router = A device using ip addresses to move traffic between networks.

Switch = A device using MAC addresses to move traffic inside a LAN.

---

# Task 1 — MAC Addresses

# MAC Address

## What does MAC stand for?
The MAC in MAC address stands for Media Access Control.
_____________________________________________________________

_____________________________________________________________

---

## What is a MAC address?
A MAC address is a unique 12 digit hexadecimal identifier assigned to a device's Network Interface Controller, or NIC. It is used to ensure data packets reach the correct hardware in a network segment.


---

## Why does every network card have a MAC address?
Every NIC has a MAC address because it serves as a unique hardware identifier burned into the ROM of the device when it is manufactured. 
Note: MAC addresses are usually assigned by the manufacturer and serve as a unique identifier for a network interface. (Graded)

---

## What OSI layer uses MAC addresses?
The OSI layer that uses the MAC address is layer 2, or the data link layer. 
_____________________________________________________________

_____________________________________________________________

---

## What is Layer 2?
Layer 2 of the OSI model is called the data link layer, which is responsible for node-to-node data transfer between directly connected devices on a network segment. 

---

# MAC Address vs IP Address

## MAC Address

What is it used for?
MAC addresses are used for local identification and direct communication between devices within a single network segment. 

---

## IP Address

What is it used for?
An IP address is used for global identification and routing of data across different networks, including the internet. 

---

## Difference Between MAC and IP

Explain the difference in your own words.
In my own words, a MAC address are used for local identification and communication within a small netword segment, mainly used for facilitating communication between two devices. In contrast, an IP address is used for global identification and moving data across different networks as a whole, like the internet, not just in a small LAN.

---

# Practice Commands

## Command

```bash
ip link
    #This command allows you to display and manage network interfaces (particularly the link layer devices) in Linux. When input, it displays all the available network interfaces, showing their state, MTU (Maximum Transmission Unit), MAC address, and link type. 
```

### What does this command do?
This command lets you display and manage link layer network interfaces on your Linux system.
Note: I struggled understanding the output of this command, as it was difficult trying to find the VM interface name using it. I need more practice with this. 

---

## Linux VM Network Interface

### Interface Name
enp0s3
________________________________________

---

### MAC Address
08:00:27:b3:dc:43
________________________________________

---

## Why is the MAC address important?
The MAC address is important because it is how devices are identified on a local network, and they help facilitate communication between devices on a single network segment. 
Note: MAC addresses allow devices on the same LAN to identify and communicate with one another. (Graded)

---

# Task 2 — Switches

# Switch

## What is a switch?
A switch is a networking device that performs the switching process on a network. 
Note: A switch is a networking device that connects devices within a LAN and forwards traffic using MAC addresses. (Graded)

---

## What does a switch do?
A switch connects network devices to one another, such as computers and servers. 

---

## What information does a switch use to forward traffic?
A switch uses destination MAC addresses in order to forward traffic to desired destinations. The traffic takes the form of packets, and uses the MAC addresses to forward them to the desired location. 
Note: Actually takes the form of frames in layer 2, not packets. (Graded)

---

# MAC Address Table

## What is a MAC address table?
A MAC address table is a data structure used by network switches to map MAC addresses to specific switch ports.
Note: It is also called a Content Addressable memory (CAM) table. 


---

## Why does a switch keep a MAC address table?
A switch keeps a MAC address table to help direct traffic directly to the righ destination, being able to send packets to the right ports. 


---

# Switches vs Hubs

## What is a hub?
A hub is a networking device used to connect multiple devices within a LAN, acting as a central connection point for data transmission. 


---

## Why is a switch better than a hub?
A hub sends copies of packets it recieves to every other device connected to, causing traffic problems. A switch sends packets only to it's destination, not to everything connected to it. 


---

## What problem does a switch solve?
The problem that a switch solves is traffic congestion, as while a hub sends a copy of a packet to everything it is connected to, a switch only sends packets to their desired destination, eliminating this congestion and making the process a lot smoother. 
Note: A switch reduces unnecessary traffic by sending data only where it needs to go. (Graded)

---

# Networking Concept

## How does a switch know where to send data?
A switch knows where to send data because of the MAC addresses that each device has. It uses a MAC address table to help direct this traffic, sending the packets to the desired location. 
_

---

# Task 3 — Expanded Network Diagram

# Updated Home Network Diagram

Draw your network below.

Internet (ISP: Visu)
|
ASUS AX5400 Router
|
Switch (ASUS AX5400)
|
Access Point (ASUS AX5400)
|
Extenders (Repeaters)
|
Msi GF63 Gaming Laptop
    Other Devices Include:
        Home PC
        Phones
        Other Laptops
        Tablets
        Amazon Firestick
|
VirtualBox Network Adapter
|
Ubuntu VM

Note: What should have been diagramed is this:

Internet
    |
ISP
    |
ASUS AX5400 Router
    |
------------------------------------------------
|              |              |               |
Laptop      Home PC      Fire Stick      Wi-Fi Devices
|
VirtualBox Adapter
|
Ubuntu VM
MAC: 08:00:27:b3:dc:43

---

# Device Information

## Router

Model:
ASUS AX5400
________________________________________

MAC Address (if known):
Don't know 
________________________________________

---

## Main Computer

Device Name:
Msi GF63 Gaming Laptop
________________________________________

IP Address:
192.168.50.190
________________________________________

MAC Address:
04:7C:16:B0:54:7D
________________________________________

---

## Virtual Machine

VM Name:
Linux Practice
________________________________________

IP Address:
10.0.2.15
________________________________________

MAC Address:
08:00:27:b3:dc:43
________________________________________

---

## Other Devices (Optional)

Phone:
iPhone 14 (2 of them)
Samsung Galaxy Fold z7
iPhone 12
iPhone 13 Pro Max
________________________________________

Tablet:
iPad Pro
iPad Pro (Newer model)
________________________________________

Game Console:
None
________________________________________

Smart TV:
Amazon Firestick
________________________________________

---

# Reflection

## What is the biggest difference between an IP address and a MAC address?
IP addresses are global identifiers used for moving data across networks, while MAC addresses are local identifiers that are used for moving data between devices on a small network segment. 


---

## Why are switches important in modern networks?
They are important in modern networks because networks are more complicated nowadays than before, and having switches allows for the data traffic to be controlled more easily and efficiently than with something like a hub. 
Note: Switches are important because they learn MAC addresses and send traffic only to the device that needs it, reducing congestion and improving efficiency compared to hubs. (Graded)

---

## What concept was most confusing today?
I would say the layer 2 model was the most confusing concept, as explaing the conceptial parts of networking like that has always been difficult for me, and trying to apply that knowledge will be a little tough. But with that said, practice with help with these concepts. 


---