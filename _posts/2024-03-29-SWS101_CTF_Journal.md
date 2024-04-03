---
Title: SWS101 Ignite
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![alt text](../assets/ignite/Screenshot_from_2024-04-02_13-21-20-removebg-preview.png)
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

When I sneak around the website I found username and password to login. 

![login](../assets/ignite/igniteadmid.png)

![login](../assets/ignite/ignitelogin.png)

After logging in, this is what I got.
![desktop](../assets/ignite/ignitedesktop.png)

when I search more about it I found it's vulnerablities.
we can perform Remote Code Execution.

![alt text](../assets/ignite/ignitevuln.png)

![search sploit](../assets/ignite/searchsploit.png)

Got more information...

![enumeration](../assets/ignite/igniteenumeration.png)

First download the script and lets try RCE. 
Got a shell and found the flag
![flag 1](../assets/ignite/flag1.png)


### Privilage Escalation

Lets try to get root account

![linpease](../assets/ignite/linpeas.png)

![fuel](../assets/ignite/ignitefuel.png)

![application](../assets/ignite/igniteapplication.png)

![config](../assets/ignite/igniteconfig.png)

![database](../assets/ignite/ignitedb.png)

![root password](../assets/ignite/rootpsw.png)

I got the root password.
Now, to access the root I have to get a reverse shell to retrive the flag. 

