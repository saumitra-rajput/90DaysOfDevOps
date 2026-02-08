# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

## Task


---

## Challenge Tasks

### Task 1: DNS – How Names Become IPs
1. Explain in 3–4 lines: what happens when you type `google.com` in a browser?

In networking each device or service has a IP address a unique idenitity on the internet.
When you type google.com > our browser give the output for the IP address for google.com
Google.com is domain name server.

GPT


-    Deep DevOps-style flow (DNS → TCP → TLS → HTTP)

-    DNS: Browser queries DNS to resolve google.com to an IP address (cached → recursive resolver → authoritative DNS).

-    TCP: A TCP 3-way handshake (SYN, SYN-ACK, ACK) is established with the server on port 443.

-    TLS: TLS handshake happens to encrypt the connection and verify the server certificate.

-    HTTP: Browser sends an HTTPS GET request; the server responds, and the browser renders the page.
2. What are these record types? Write one line each:
   - `A`: IP address 4 
   - `AAAA`: IP address 4 and 6
   - `CNAME`: Logical subdomain for the DNS
   - `MX`: Mail 
   - `NS`: Name server
   - A: Maps a domain name to an IPv4 address. 
   - AAAA: Maps a domain name to an IPv6 address. 
   - CNAME: Points one domain (alias) to another domain name. 
   - MX: Specifies the mail server responsible for receiving emails for a domain. 
   - NS: Identifies the authoritative name servers for a domain.
3. Run: `dig google.com` — identify the A record and TTL from the output


```
;; ANSWER SECTION:
google.com.             134     IN      A       142.250.190.142
```
---

### Task 2: IP Addressing
1. What is an IPv4 address? How is it structured? (e.g., `192.168.1.10`)

An IPv4 address is a 32-bit numerical identifier used to uniquely identify a device on a network.

It is written in dotted-decimal format with four octets (0–255), e.g. 192.168.1.10.

2. Difference between **public** and **private** IPs — give one example of each

Public IP: Routable on the internet and globally unique (e.g. 8.8.8.8).

Private IP: Used inside local networks and not routable on the internet (e.g. 192.168.1.10).

3. What are the private IP ranges?

10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255

   - `10.x.x.x`, `172.16.x.x – 172.31.x.x`, `192.168.x.x`
4. Run: `ip addr show` — identify which of your IPs are private

2: ens5: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc mq state UP group default qlen 1000
    link/ether 06:67:4a:0c:ae:6f brd ff:ff:ff:ff:ff:ff
    inet 172.31.19.31/20 metric 100 brd 172.31.31.255 scope global dynamic ens5

    Private IP 172.31.19.31/20
---

### Task 3: CIDR & Subnetting
1. What does `/24` mean in `192.168.1.0/24`?

/24 means 24 bits are reserved for the network part of the IP address, leaving 8 bits for hosts in that network.
2. How many usable hosts in a `/24`? A `/16`? A `/28`?

Formula: 2^(host bits) − 2

/24 → 8 host bits → 254 usable hosts

/16 → 16 host bits → 65,534 usable hosts

/28 → 4 host bits → 14 usable hosts

3. Explain in your own words: why do we subnet?

We subnet to divide large networks into smaller ones to reduce broadcast traffic, improve security, and manage IP addresses efficiently.

4. Quick exercise — fill in:

| CIDR | Subnet Mask     | Total IPs | Usable Hosts |
| ---- | --------------- | --------- | ------------ |
| /24  | 255.255.255.0   | 256       | 254          |
| /16  | 255.255.0.0     | 65,536    | 65,534       |
| /28  | 255.255.255.240 | 16        | 14           |

| CIDR | Subnet Mask | Total IPs | Usable Hosts |
|------|-------------|-----------|--------------|
| /24  | ?           | ?         | ?            |
| /16  | ?           | ?         | ?            |
| /28  | ?           | ?         | ?            |

---

### Task 4: Ports – The Doors to Services
1. What is a port? Why do we need them?
A port is a logical communication endpoint on a device that identifies a specific service or application.


We need ports so multiple services can run on the same IP address without conflicts (e.g., web, SSH, database all on one server).
2. Document these common ports:

| Port | Service |
|------|---------|
| 22   | SSH     |
| 80   | HTTP    |
| 443  | HTTPS   |
| 53   | DNS     |
| 3306 | MYsql   |
| 6379 | Redis   | 
| 27017| MongoDB |
| 3389 | RDP     |

3. Run `ss -tulpn` — match at least 2 listening ports to their services
```
tcp             LISTEN           0                4096                                 0.0.0.0:22                             0.0.0.0:*                                
tcp             LISTEN           0                4096                           127.0.0.53%lo:53                             0.0.0.0:*                                
tcp             LISTEN           0                4096                              127.0.0.54:53                             0.0.0.0:*                                
tcp             LISTEN           0                4096                                    [::]:22                                [::]:*        
```
---

### Task 5: Putting It Together
Answer in 2–3 lines each:
- You run `curl http://myapp.com:8080` — what networking concepts from today are involved?

DNS resolves myapp.com to an IP address, then a TCP connection is made to port 8080.
An HTTP request is sent to the application service listening on that port and the response is returned.
- Your app can't reach a database at `10.0.1.50:3306` — what would you check first?

First, verify network reachability (same VPC/VNet, routing, subnet).
Then check firewall / security group rules allowing port 3306, and confirm the database service is running and listening.
---
