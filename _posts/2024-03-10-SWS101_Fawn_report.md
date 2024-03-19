---
Title: SWS101 Fawn Report
categories: [SWS101,HACK THE BOX TIER_0]
tags: SWS 101
---

# Fawn 
![Fawn](/assets/img/fawn.jpeg)

## Executive Summary
In this penetration test I explored Fawn hosted on hack The Box(HTB) with the goal of accessing system security my ability to gain full access to the system. The primary goal of this penetration test is to find the "flag.txt".
## Penetration Test Report
Target: 10.129.220.120

## Information Gathering Phase
Port Scanning with Nmap:


        nmap -sV -vv 10.129.220.120


![check flag](/assets/img/nmap.png)

* One open port discovered: 21/tcp (FTP).
* Service version identified: “vsFTPd 3.0.3.”
* OS: unix


        ftp 10.129.220.120

Results of FTP Enumeration:
![check flag](/assets/img/login.png)

* Results of FTP Enumeration.
* Logged in anonymously.

## Exploitation Phase
* Check for “flag.txt” file.

        ls


![check flag](/assets/img/checkflag.png)

        get flag.txt


* Retrieved the contents of “flag.txt” using the “get”command.
![get flag](/assets/img/get.png)

## Conclusion
This penetration test shows our ability to access sensitive information.


