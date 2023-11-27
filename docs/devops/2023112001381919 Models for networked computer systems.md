---
tags:
  - osi
  - tcp/ip 
---
# Models for networked computer systems
## TCP/IP model
1. **The Network Access Layer or Link Layer** : hardware
2. **The Internet Layer**: IP protocols (IPv4 or IPv6.)
3. **The Transport Layer**: TCP and UDP.
4. **The Application Layer**: HTTP and HTTPS
## OSI model

| OSI | TCP/IP |
|-----------------| ---------------------|
|Application Layer |Application Layer  HTTP/HTTPS|
|Presentation Layer |Application Layer  HTTP/HTTPS |
|Session Layer | Application Layer  HTTP/HTTPS|
|Transport Layer | Transport Layer TCP/UDP |
|Network Layer | Internet Layer IP |
|Data link Layer | Network Access Layer hardware |
|Physical Layer | Network Access Layer hardware |

## TCP
- It is protocols that works with IP to transmit data. It is accuracy.
## UDP
-  is mainly used for streaming applications
- faster then TCP and it's error-prone

## WebSockets
- is more resource-intensive and adds complexity.
- cases:
	- messaging services
	- gaming
	- trading platforms
## References
1. [System Design Interview Course](https://www.tryexponent.com/courses/system-design-interview/fundamentals-system-design/web-protocols)