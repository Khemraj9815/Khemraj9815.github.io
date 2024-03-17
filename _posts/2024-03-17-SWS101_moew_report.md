---
Title: SWS101 Flipped_class
categories: [SWS101,Meow Report]
tags: SWS 101
---
# Meow
![meow](/assets/img/moew.jpeg)

## Executive Summary
This panetration test was conducted on the target machine Meow of the hack the box. The Objective of this penetration test is to check the security of the system and our ability to access the sensitive information in the system. The primary goal is the find the "flag.txt" and retrive it.
 
## Penetration Test Report
Target: 10.129.30.253

## Information Gathering Phase:
Port Scanning with Nmap:
![nmapmeow](/assets/img/nmapmeow.png)

*  The target system had only one open port: 23/tcp (Telnet).
* Service version identified as “Linux telnetd.”
* Operating system detected as “Linux.”

## Enumeration of Telnet Service:
### Enumerate Telnet:
* command used: "telnet 10.129.30.253"

## Results of Telnet Enumeration:
* Logged in as the root user.
* System identified as running Ubuntu 20.04.2 LTS with a Linux kernel version of 5.4.0–77-generic.

![meow login](/assets/img/meow_login.png)

## Exploitation Phase
* check for the flag.txt.
* Finally got the flag.
![get flag](/assets/img/meowflag.png)

## Conclusion
The system was found to have a Telnet service running with default credentials, which allowed us to gain root access and retrieve the flag.

