---
Title: SWS101 Ignite
categories: [SWS101,CTF Journal]
tags: SWS 101
---




## Executive Summary


## Penetration Test Report
Target: 10.10.51.128


## Information Gathering Phase

Port Scanning with Nmap:

        nmap -sV -sC -vv 10.10.51.128

![nmap](../assets/ignite/igntenmap.png)

* port 80 is open.
![port 80](../assets/ignite/ignitegoogleport80.png)

* machine is running Apache HTTP Server version 2.4.18 on Ubuntu.
* Fuel CMS version 1.4.1 is running on the server.
*  a disallowed entry in the robots.txt file for the path /fuel/.

This is web page for given ip address.

![webpage](../assets/ignite/ignitewebpage.png)

got extra imformation.

![login](../assets/ignite/igniteadmid.png)

![search sploit](../assets/ignite/igniteenumeration.png)

we can perform Remote Code Execution.

![alt text](../assets/ignite/ignitevuln.png)

Lets try RCE which is given above "php/webapps/50477.py"






