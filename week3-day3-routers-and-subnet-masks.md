# Active Learning Day 3 — Routers & Subnet Masks

## Warm-Up — Multiple Choice Quiz

Try these WITHOUT notes.

---

## 1. Which device primarily forwards traffic between different networks?

A) Switch  
B) Router  
C) Hub  
D) Access Point

Answer: B

---

## 2. Which device primarily forwards traffic using MAC addresses?

A) Router  
B) DNS Server  
C) Switch  
D) DHCP Server

Answer: C

---

## 3. What is the main job of a router?

A) Assign MAC addresses  
B) Connect devices within a single LAN only  
C) Move traffic between different networks  
D) Store DNS records

Answer: c

---

## 4. What information does a router primarily use to make forwarding decisions?

A) MAC Addresses  
B) IP Addresses  
C) Hostnames  
D) Usernames

Answer: b

---

## 5. What is a default gateway?

A) The first MAC address on a network  
B) A backup switch  
C) The device used to reach other networks  
D) A DNS server

Answer: c

---

## 6. What does a subnet mask help determine?

A) Which packets are encrypted  
B) Which part of an IP address is the network and which part is the host  
C) Which MAC address belongs to a device  
D) Which DNS server to use

Answer: b

---

# Router vs Switch

## Which statement best describes a router?

A) Uses MAC addresses to move traffic inside a LAN  
B) Uses IP addresses to move traffic between networks  
C) Assigns IP addresses automatically  
D) Translates domain names

Answer: b

---

## Which statement best describes a switch?

A) Uses IP addresses to move traffic between networks  
B) Uses MAC addresses to move traffic inside a LAN  
C) Assigns DNS records  
D) Creates subnet masks

Answer: b

---

## In Your Own Words

### What is the difference between a router and a switch?
A router uses IP addresses to move traffic between networks, while a switch used MAC addresses to move traffic inside a LAN, between devices.

---

# Task 1 — Routers

# Router

## What is a router?
A router is a networking device that uses IP addresses to move traffic between other networks. It is an essential component of networking. 


---

## Why do networks need routers?
Routers are needed because they allow communication between devices that are otherwise isolated. Another factor why they are needed is because they act as traffic directors, determining the best path for information to reach destination across a network. 

---

## What information does a router use to forward traffic?

A) MAC Addresses

B) IP Addresses

C) Domain Names

D) Usernames

Answer: B

---

# Default Gateway

## What is a default gateway?
A default gateway is a network device that serves as the access point for devices on a local network to communicate with an external network. 

---

## Why is the default gateway important?
A default gateway is important because it allows for interaction with external networks, such as the internet. 


---

# Routing

## What is routing?
Routing is the process of selecting a path across one or multiple networks. 


---

## Why is routing important?
Routing is important because is selects the most efficient path for data to take in order to get to their destination. 
Example:
Say there are two routes that the data can take to get to it's desitination, one with 2 networks and one with 3. You might think the route with 2 networks is best, but the route with 3 networks might be faster than the other one. Routers make these decisions to ensure the most efficient path for the data to travel on. 

---

# Different Networks

## Why can't devices on different networks always communicate directly?
Devices on different networks can't communicate directly because they are seperated by subnets (logical network boundaries). 
Note: Devices on different networks cannot communicate directly because they belong to different IP networks. They require a router to move traffic between those networks. (Graded)

---

## How do routers help solve this problem?
Router solve this problem by facilitating the traffic between the different networks by comparing the destination IP address against its own subnet mask, determining whether to send a packet to its default gateway or attempting direct layer 2 communication. 
Note: Routers receive packets destined for other networks and forward them toward the correct destination network. (Graded)

---

# Practice Commands

## Command

```bash
ip route
    #This command lets you display, add, delete, and modify entries in the system's IP routing table. 
```

### What does this command do?
When I input this command, it displayed information about the current routing table entries. 


---

# Questions

## What is your default gateway?
The default gateway for my vm seems to be 10.0.2.2.


---

## Why do we need routers?
Routers are necessary because they help facilitate communication between different networks, and help direct the traffic between those networks in order to determine the best path for the data to travel in order for it to reach its destination. 


---

# Task 2 — Subnet Masks

# Subnet Mask

## What is a subnet mask?
A subnet mask is a 32 bit number that separates an IP address into network and host portions. 


---

## What does a subnet mask do?

A) Assigns IP addresses

B) Identifies the network portion and host portion of an IP address

C) Translates domain names

D) Stores MAC addresses

Answer: B

---

# Network Portion

## What is the network portion of an IP address?
The network portion of an IP address is the segment that identifies the specific network/subnet that a device belongs to. 


---

## Why is the network portion important?
The network portion of an IP address is important because it allows routers to determine the correct path for forwarding data. 

---

# Host Portion

## What is the host portion of an IP address?
The host portion of an IP address is the segment that identifies a specific device on a network. 


---

## Why is the host portion important?
The host portion of an IP address is important because it helps identify devices within a designated network, helping ensure the data reach the intended location. 


---

# Common Subnet Mask

## Example

```text
255.255.255.0
```

### What is this?
The number above is a subnet mask for a /24 network. 


---

## Why is 255.255.255.0 so common?
The reason why this subnet mask is so common is because it provides a good balance of capacity and control. It is because of this that it is a bunch of SOHO (small office home office) and small work LANs. 


---

# Concept Check

## If two devices have the same network portion, what does that usually mean?

A) They are on the same network

B) They are on different networks

C) They have the same MAC address

D) They are the same device

Answer: a

---

## If two devices are on different networks, what device usually helps them communicate?

A) Hub

B) Access Point

C) Router

D) Repeater

Answer: c

---

## In Your Own Words

### What does a subnet mask help a device understand?
A subnet mask helps a device identify both the network the device is on and where to send data to. 
Note: A subnet mask helps a device determine which part of an IP address identifies the network and which part identifies the host. This allows the device to determine whether a destination is on the local network or whether it must send the traffic to a router. (Graded)

---

# Task 3 — TryHackMe Notes

# Introductory Networking

## Important Concepts Learned
OSI Model (Open Systems Interconnection)
    Layer 7: Appliation
        This layer provides networking options to programs running on a computer. When data is given here, it is passed down to the presentation layer. 
    Layer 6: Presentation
        This layer translates the data into a standardised format, as well as handling any transformations to the data. The data is passed to the session layer when complete.
    Layer 5: Session
        This layer sets up a connection with the other computer across a network. When the connection between the host and remote omputer is logged, the data is passed down to the transport layer. 
    Layer 4: Transport
        This layer chooses the protocol over which the data is to be transmitted (TCP and UDP). After the protocol is selected, it then divides the transmission up into bite-sized pieces, which makes it easier to transmit the message successfully. 
    Layer 3: Network
        This layer locates the destination of your request, and finds the best route for it to take. 
    Layer 2: Data Link
        This layer recieves a packet from the network layer and adds in the physical (MAC) address of the receiving endpoint. It is also the job of this layer to present the data in a format suitable for transmission. This layer also checks the received informatino to make sure that it hasn't been corrupted during transmission. 
        Note: Layer 2 handles MAC addressing, framing, and error detection on the local network. (Graded)
    Layer 1: Physical
        This layer is where the electrical pulses that make up data transfer over a network are sent and received. 
Encapsulation
    Encapsulation is the process by which data can be sent from one computer to another. The more layers the data goes down, the more information based on the specific layer in question is added. 
    Note: Encapsulation does provide an extra layer of security. 
        Note: Encapsulation organizes data so different networking protocols can work together. (Graded)
    De-encapsulation
        When the message is received by the second computer, it starts from layer 1 and goes up to 7, the reverse of sending information. 
The TCP/IP Model (Transmission Control Protocol) (Internet Protocol)
    Application
        Contains layers 7-5 of the OSI model.
    Transport
        Same as layer 4 of the OSI model. 
    Internet
        Same as layer 3 of the OSI model.
    Network Interface
        Contains layers 2-1 of the OSI model. 
    TCP controls the flow of data between two endpoints, and IP controls how packets are addressed and sent. 
    Three-way handshake
        When an attempt is made to make a connection, the computer first sends a special request to the remote server indicating that it wants ti initialise a connection, containing something called a SYN (synchronise).
        The server will respond with a packet containg the SYN bit as as an ACK bit (acknowledgement). 
        The computer will then send a packet that contain just the ACK bit by itself, confirming the connection was successful. 
        With this process completed, data can be reliably transmitted between computers. 
Domain Names
    Domains make it so where we don't have to remember the IP address of every website we want to visit. 
    DNS (Domain Name System)
        DNS allows us to aks a special server to gives us the IP address of the website we're trying to access.
## Important Commands Learned
``` bash
ping
    #This command lets you test to see if a connection to a remote resource is possible. 
    #Note: In order to stop the ping command, use Ctrl C to stop it. 
    ping google.com
        #This command tests whether a connection to google is possible or not. 
        #Note: Tests whether a remote host responds to ICMP Echo Requests. (Graded)
    -i
        #This flag lets you change the interval of sent ping requests.
    -4
        #This flag lets you restrict requests to IPv4.
    -v
        #This flag gives you a more verbose output. 
traceroute
    #This command lets you map the path of your request takes as it heads to your desired resource.
    traceroute google.com
        #This command maps the path the request takes to get to google.com
whois
    #This command lets you see who a domain name is registered to. 
    whois bbc.co.uk
        #This command will display the available information about the bbc.co.uk domain. 
dig 
    #This command lets you query DNS name servers and troubleshoot DNS issues. 
    dig google.com @8.8.8.8
        #This command queried google.com, giving us the DNS info about it. 
```

# What concept was most confusing?
I would say the DNS information was the most confusing to me, as it was a lot of information at once, and very theory heavy for me, which I find difficult sometimes.


---

# What concept felt easiest?
The ping command felt the easiest to me, as it was fairly self explanatory. 


---

# End-of-Day Reflection

## Explain a router in your own words.
A router is a networking device that moves traffic from one network to another. 

---

## Explain a subnet mask in your own words.
A subnet mask is a number that identifies the network portion and a host portion of an IP address. 


---

## How confident do you feel with routers and subnet masks?

2.5/10