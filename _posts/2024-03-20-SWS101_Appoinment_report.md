---
Title: SWS101 Appointment Report
categories: [SWS101,HACK THE BOX TIER_1]
tags: SWS 101
---

![appoinment](/assets/img/appoinment.png)

## Executive Summary
In this penetration test I am exploring appointment machine hosted on hack the box
(HTB) with the aim of accessing system security and our primary goal is to get the flag.txt
## Penetration Test Report
Target: 10.129.245.180

## Information Gathering Phase:
Port Scanning with Nmap:

        nmap -sV -vv 10.129.245.180

![nmap](/assets/img/appointmentnmap.png)

* The target machine has the HTTP service running on port 80.

![ip address](/assets/img/appointmentip.png)
![login form](/assets/img/appointmentloginform.png)

I don't know the username and password for it.
After reading many documentation I found cheat sheet to see which username and password to use to login. 

![sql cheat](/assets/img/appoinmentsqlcheat.png)

I used special character('#) where where it tells system to ignore everything after it, so it doesn't check for password. This will let us login as admin without knowing password.

![appointment flag](/assets/img/appointmentflag.png)

### Conclusion 
This penetration test demonstrate our ability to bypass authentication and gain admin access. So to gain admin access we implemented sql injection.