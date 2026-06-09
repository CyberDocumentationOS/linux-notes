# Week 4 — Day 1
# TCP vs UDP

---

# Warm-Up — Multiple Choice Review

Try these WITHOUT notes.

---

## 1. Which permission string represents `chmod 644`?

A) rwxrwxrwx

B) rw-r--r--

C) rwx------

D) rwxrwx---

Answer: b

---

## 2. Which command shows the groups a user belongs to?

A) groups

B) pwd

C) chmod

D) touch

Answer: a

---

## 3. What is the primary purpose of an IP address?

A) Identify a device on a network

B) Identify a user account

C) Store files

D) Identify a MAC address

Answer: a

---

## 4. Which device primarily forwards traffic using MAC addresses?

A) Router

B) Switch

C) DNS Server

D) DHCP Server

Answer: b

---

## 5. Which device primarily forwards traffic between different networks?

A) Hub

B) Switch

C) Router

D) Access Point

Answer: c

---

## 6. What does DNS do?

A) Assigns IP addresses automatically

B) Routes traffic

C) Translates domain names into IP addresses

D) Stores MAC addresses

Answer: c

---

## 7. What does DHCP do?

A) Assigns IP addresses automatically

B) Translates domain names

C) Routes traffic

D) Stores MAC addresses

Answer: a

---

## 8. Which command displays your routing table?

A) ip addr

B) ip link

C) ip route

D) hostname -I

Answer: c

---

# Task 1 — TCP

# TCP
Transmission Control Protocol

---

## Multiple Choice

### What is TCP?

A) A protocol focused on speed above all else

B) A reliable connection-oriented transport protocol

C) A type of router

D) A DNS service

Answer: b
---

### Which OSI/TCP-IP layer primarily uses TCP?

A) Physical Layer

B) Data Link Layer

C) Transport Layer

D) Application Layer

Answer: c

---

## Short Answer

### What does TCP stand for?
Transmission Control Protocol


---

### Why is TCP considered reliable?
TCP is considered reliable because it guarantees the error-free, in-order, and non-duplicate delivery of data streams over an unreliable network. 

---

### What is an ACK?
The ACK (Acknowledge) bit is a signal used in digital communication protocols (such as the Three-way Handshake) to confirm the successful reciept of data. 


---

# Three-Way Handshake

## Multiple Choice

### Which packet is sent first?

A) ACK

B) SYN

C) SYN-ACK

D) HTTP

Answer: b

---

## Fill In The Blanks

Step 1:

Client sends a SYN packet.

---

Step 2:

Server responds with a SYN-ACK packet.

---

Step 3:

Client sends an ACK packet.

---

### What is the purpose of the three-way handshake?
The purpose of the three-way handshake is to establish a reliable, bidirectional TCP connection between a client and a server before application data is transmitted. 


---

# Retransmission

## Short Answer

### What happens if a packet is lost?
When a packet is lost, it doesn't reach it's destination or comes too late to become useful, creating gaps in the data stream. This forces retransmission, which increases latency. 


---

### Why is retransmission important?
Retransmission is important because it ensures that data reaches its destination intact and in order, which is critical for protocols like TCP.  


---

# In Your Own Words

### Explain TCP like you're teaching a beginner.
TCP is a reliable connection oriented transport protocol that operates in layer 4 of the OSI model. It is considered reliable because of its guarantee of error-free, in-order, and non-duplicate delivery of data streams over networks, even unreliable ones. 


---

# Task 2 — UDP

# UDP
User Datagram Protocol

---

## Multiple Choice

### What is UDP?

A) A reliable connection-oriented protocol

B) A routing protocol

C) A fast connectionless transport protocol

D) A DNS server

Answer: c
---

### Which characteristic best describes UDP?

A) Reliability

B) Speed

C) Retransmission

D) Error Recovery

Answer: b

---

## Short Answer

### What does UDP stand for?
User Datagram Protocol

---

### What does connectionless mean?
Connectionless means the protocol does not establish a dedicated connection or a guarantee of packet delivery, ordering, or error correction, which means there are no retransmission attempts. 


---

### Why is UDP generally faster than TCP?
Because of the lack of connection/retransmission, UDP is able to focus on time-sensitivty rather than reliability. This is more used for applications where data flow is more critical than perfect accuracy. 


---

# Speed vs Reliability

## Multiple Choice

### Does UDP use a three-way handshake?

A) Yes

B) No

Answer: b

---

### Does UDP retransmit lost packets?

A) Yes

B) No

Answer: b

---

## Short Answer

### What is the tradeoff when using UDP?
When using UDP, you are sacrificing reliability for more spontainious expierence. 
Note: sacrificing reliability for speed and lower latency (Graded)

---

### Why do online games often use UDP?
Online games require constant connection to the internet and are quite intensive when it comes to that regard, so using UDP is the more logical choice. 
Note: Online games use UDP because receiving the newest information quickly is usually more important than receiving every packet perfectly. (Graded)

---

# In Your Own Words

### Explain UDP like you're teaching a beginner.
UDP is a fast connectionless oriented transport protocol in layer 4 of the OSI model. It does not use a dedicated connection or retransmission, which allows for faster network speeds than TCP. 

---

# Task 3 — TCP vs UDP Comparison

# TCP vs UDP

## Fill In The Table

| Category | TCP | UDP |
|-----------|-----------|-----------|
| Reliable? | yes | no |
| Uses Handshake? | yes | no |
| Retransmits Lost Packets? | yes | no |
| Faster? | no | yes |
| Connection-Oriented? | yes | no |
| Connectionless? | no | yes |

---

## Examples of TCP Usage

Give three examples:

1. Remote access.

2. Downloading a file.

3. Web browsing.

---

## Examples of UDP Usage

Give three examples:

1. Online Gaming

2. Video streaming

3. DNS

---

## Which would you choose?

### For loading a website?

TCP or UDP: TCP

Why?
You want to make sure that the entire website is able to load fully, as we want 100% of it to work. 

---

### For an online multiplayer game?

TCP or UDP: UDP

Why?
Because of how they are structured, it is more important for us to get to where we want to go quickly rather than making sure every packet is perfect.
Note: UDP reduces overhead by not requiring acknowledgements, retransmissions, or connection setup. (Graded)

---

### For downloading a file?

TCP or UDP: TCP

Why?
When we are downloading a file, we want 100% of it to be there, as it may not work if we don't have all the data. 

---

# Reflection

## What is the biggest difference between TCP and UDP?
The TCP protocol is all about reliability and making sure every packet is transmitted fully, while the UDP protocol is more about speed and making sure packets are transmitted quickly. 


---

## Which protocol seems more useful for cybersecurity work?

Why?
It really depends on what the specific task is at hand. If is something like analyzing an error log, then we would want the protocol to be TCP, as having all the data is crucial for examining what happened. But if it is something like stopping a real time attack, then using UDP is more efficient, as it doesn't matter if every packet is transmitted perfectly, we just need to get to where we need to in order to stop the attack. There is no one answer that is correct for all of cybersecurity, as there is a use for everything. 

---