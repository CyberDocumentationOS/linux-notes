# Week 4 — Day 3: HTTP, HTTPS, SSH & FTP

**Estimated Time:** 1.5–2 Hours

---

# Warm-Up — Multiple Choice Review

Try these WITHOUT notes.

---

## 1. What is the primary purpose of an IP address?

A) Identify a device on a network

B) Identify a user account

C) Identify a MAC address

D) Store files

Answer: a

---

## 2. What is a MAC address?

A) A logical network address

B) A unique hardware address assigned to a network interface

C) A DNS record

D) A subnet mask

Answer: b

---

## 3. What does DHCP do?

A) Translates domain names

B) Assigns IP addresses automatically

C) Routes traffic

D) Stores MAC addresses

Answer: b

---

## 4. What does a subnet mask help determine?

A) Which DNS server to use

B) Which website to visit

C) Which part of an IP address is the network and which part is the host

D) Which MAC address belongs to a device

Answer: c

---

## 5. What is a default gateway?

A) A backup DNS server

B) A subnet mask

C) The device used to reach other networks

D) A MAC address

Answer: c

---

## 6. Which device primarily forwards traffic using MAC addresses?

A) Router

B) Switch

C) DNS Server

D) DHCP Server

Answer: b

---

## 7. Which device primarily forwards traffic between different networks?

A) Hub

B) Switch

C) Router

D) Access Point

Answer: c

---

## 8. Which private IP range is commonly used in home networks?

A) 8.8.8.8

B) 1.1.1.1

C) 127.0.0.1

D) 192.168.x.x

Answer: d

---

# Task 1 — HTTP & HTTPS

# HTTP
HyperText Transfer Protocol

---

## Multiple Choice

### What is HTTP?

A) A protocol used for transferring web pages and web content

B) A protocol used for assigning IP addresses

C) A routing protocol

D) A file permission system

Answer: a

---

### Which default port does HTTP use?

A) 22

B) 80

C) 443

D) 53

Answer: b

---

## Short Answer

### What does HTTP stand for?
Hypertext Transfer Protocol

---

### What is HTTP used for?
HTTP is used to transfer data over the internet, allowing the world wide web to function. 

---

### Is HTTP encrypted?

A) Yes

B) No

Answer: b

---

# HTTPS
HyperText Transfer Protocol Secure

---

## Multiple Choice

### What is HTTPS?

A) A secure version of HTTP

B) A secure version of FTP

C) A DNS service

D) A routing protocol

Answer: a

---

### Which default port does HTTPS use?

A) 80

B) 53

C) 443

D) 22

Answer: c

---

## Short Answer

### What does HTTPS stand for?
Hypertext Transfer Protocol Secure


---

### What is HTTPS used for?
HTTPS is mainly used to encrypt data transmitted between a web browser and a website, ensuring the sensitive information remains private and protected from interception. 


---

# Encryption

## Multiple Choice

### What is encryption?

A) Compressing files

B) Converting readable data into unreadable data without the proper key

C) Assigning IP addresses

D) Creating MAC addresses

Answer: b

---

## Short Answer

### Why is encryption important?
Encryption is important because it helps hide sensitive information and makes sure it is secure, even if it is stolen by unauthorized parties. 


---

### Why is HTTPS safer than HTTP?
HTTPS is safer that HTTP because the latter has little security and no encryption, meaning if unauthorized parties get their hands on the data, they can see sensitive information. Because it has encryption, HTTPS is the safer choice, as it makes sure that sensitive data stays hidden. 

---

### What does HTTPS protect?
HTTPS protects data in transit between the browser and website, encrypting sensitive information and ensuring security from hackers. 


---

# Certificates

## Multiple Choice

### What is the purpose of a digital certificate?

A) To verify the identity of a website

B) To assign IP addresses

C) To create MAC addresses

D) To store files

Answer: a

---

## Short Answer

### Why are certificates important?
Certificates are important because they ensure authenticity by verifying the identity of websites, people, and devices, ensuring that all are legitmate sources and not imposters. 


---

# In Your Own Words

### Explain the difference between HTTP and HTTPS.
HTTP is the protocol that is used to transfer data over the interent, which allows the world wide web to function, while HTTPS is a more secure version of this protocol, as it encrypts certain data that contains sensitive information, ensuring private information stays private. 
Note: HTTPS encrypts the entire HTTP session between browser and server. (Graded)

---

# Task 2 — SSH & FTP

# SSH
Secure Shell

---

## Multiple Choice

### What is SSH primarily used for?

A) Remote administration of systems

B) Assigning IP addresses

C) Resolving domain names

D) Viewing web pages

Answer: a

---

### Which default port does SSH use?

A) 20

B) 21

C) 22

D) 443

Answer: c

---

## Short Answer

### What does SSH stand for?
Secure Shell


---

### What is SSH used for?
SSH is used for accessing and managing a system from a remote destination over an unsecure network. 

---

### Why is SSH useful?
SSH is useful because it provides end-to-end encryption for remote server access, replacing insecure legacy protocols that transmitted data in plain text. 


---

# FTP
File Transfer Protocol

---

## Multiple Choice

### What is FTP primarily used for?

A) Remote administration

B) File transfer

C) DNS resolution

D) Routing traffic

Answer: b

---

### Which ports are commonly associated with FTP?

A) 22

B) 53

C) 80

D) 20 and 21

Answer: d

---

## Short Answer

### What does FTP stand for?
File Transfer Protocol

---

### What is FTP used for?
FTP is used for transferring computer files between a client and a server over a TCP/IP connection. 


---

### Why is FTP considered insecure?
FTP is considered insecure due to it's lack of encryption, as it only sends data and credentials in plain text. Because of this, it is not known as a secure protocol. 


---

# SFTP

## Multiple Choice

### What does SFTP stand for?

A) Secure File Transfer Protocol

B) Simple File Transfer Protocol

C) Secure Folder Transfer Protocol

D) Shell File Transfer Protocol

Answer: a

---

### Which statement best describes SFTP?

A) FTP without authentication

B) FTP running through SSH encryption

C) HTTP with encryption

D) A DNS service

Answer: b

---

## Short Answer

### Why is SFTP preferred over FTP?
SFTP is preferred over FTP because it wraps the entire session in SSH encryption, which makes it much more secure that FTP, which only uses plain text. 
Note: SFTP is actually a different protocol that runs over SSH. (Graded)

---

# In Your Own Words

### Explain SSH to a beginner.
SSH is a protocol that is used for remote access and managment of systems over an unsecure network. It provides end-to-end encryption for every remote session, making it the optimal format to use for remote administration. 

---

### Explain why FTP is considered insecure.
FTP is considered insecure due to it's lack of encryption, having data and credentials sent in plain text which leaves the data vulnerable to hackers. 

---

# Task 3 — Protocol Comparison

# Protocol Comparison Table

| Protocol | Purpose | Default Port | Secure? |
|-----------|-----------|-----------|-----------|
| HTTP | transfer of data over the internet | 80 | no |
| HTTPS | encrypted transfer of data over the internet | 443 | yes |
| SSH | remote administration | 22 | yes |
| FTP | transferring files over tcp connection | 20/21 | no |
| SFTP | FTP running through SSH encryption | 22 | yes |

---

# Questions

## Which protocol would you use to securely access a Linux server remotely?
SSH


Why?
SSH is meant for accessing and managing systems/server remotly over an unsecure connection. Because of that, it is the best choice. 


---

## Which protocol would you use to browse a secure website?
HTTPS


Why?
HTTP doesn't encrypt data and transmits in plain text, while HTTPS encrypts data, to make sure private information stays that way. Because of that, HTTPS is the way to go. 


---

## Which protocol is generally considered insecure?
FTP


Why?
FTP transmit data in plain text, lacking encryption. This means that hackers can easily access and steal sensitive information, which is why it is considered insecure. 
Note: Anyone able to observe the network traffic can read the data. (Graded)

---

# Reflection

## Which protocol seems most useful for cybersecurity work?
SSH is definitly the most useful protocol for cybersecurity work, as the end-to-end encryption allows for remote connection over an unsecure network, which is really handy for this line of work. 


---

## Which concept was easiest today?
I would say SSH was the easiest, as it is something I touched on briefly before this, and accessing a system remotely is easy to understand from a technical standpoint (minus the intracut details).


---

## Which concept was most confusing?
I would say the most confusing concept was SFTP, particularly when it came to encryption, as it running over SSH was something I wasn't aware of before this was graded. 

---

## In one sentence, explain why encryption matters.
Encryption is important because it makes sure the data isn't readable, keeping private information private. 


---