# DNS & ICMP Network Protocol Analysis

## Overview
This project documents a **network protocol investigation** conducted as part of the Google Cybersecurity Professional Certificate on Coursera.  
The analysis focused on **DNS resolution failures** and **ICMP error responses** observed in captured network traffic for `www.yummyrecipesforme.com`.

---

## Tool Used
- **tcpdump** — for capturing and analyzing network packets.

---

## Summary of Findings
- The client system sent **DNS queries over UDP** to the DNS server at **203.0.113.2**.  
- Each query triggered **ICMP "Destination Unreachable"** responses stating **UDP port 53 unreachable**.  
- This indicates that the **DNS service was either down**, **misconfigured**, or **blocked by a firewall**.  

---

## Likely Cause
The DNS server was not listening on **UDP port 53**, or network controls were filtering traffic to that port.  
As a result, DNS resolution failed and the website became unreachable.

---

## Conclusion
The issue stemmed from a **network-layer communication failure** between the client and the DNS server.  
Proper DNS service validation and firewall configuration checks are recommended to prevent recurrence.
