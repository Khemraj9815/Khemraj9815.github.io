---
Title: SWS101 Crocodile Report
categories: [SWS101,HACK THE BOX TIER_1]
tags: SWS 101
---

![Dancing](/assets/img/crocodile.jpeg)

## Executive Summary
This panetration test was conducted on the target machine Crocodile which is hosted on hack the box. The Objective of this penetration test is to check the security of the system and our ability to access the sensitive information in the system. The primary goal is the obtain the flag.

# Penetration Test Report
Target: 10.129.1.15

## Information Gathering Phase
Port Scanning with Nmap:

        nmap -sV 10.129.1.15


![crocodile nmap](/assets/img/crocodilenmap.png)

Open ports discovered.

- Port 21/tcp: Running vsftpd 3.0.3 (FTP server).
- Port 80/tcp: Running Apache httpd 2.4.41 (Web server) on Ubuntu.

![port 21](/assets/img/crocodile/port21.png)

![port 21](/assets/img/crocodile/ftp21.png)

So we can connect to port 21 ftp server.

## Enumeration Phase

![ftp login](/assets/img/crocodile/ftplogin.png)

## Exploitation Phase
![ftp login](/assets/img/crocodile/ftp21ls.png)

We got two file. So, lets get through it.

![ftp login](/assets/img/crocodile/ftpget1.png)

![ftp login](/assets/img/crocodile/ftpget2.png)

### Results

We got both the files. Let's see what is inside those file.

![user](/assets/img/crocodile/user1.png)

I guess these are the password for allowed user.

![passwd](/assets/img/crocodile/user2.png)

This one are the for user password.

Now lets see the port 80/tcp: Running Apache httpd 2.4.41 (Web server) on Ubuntu.

![p80tcphttp](/assets/img/crocodile/p80tcphttp.png)

![p80tcphttp](/assets/img/crocodile/webpagep80.png)

Now let's brute-force to see hidden directory.

![p80tcphttp](/assets/img/crocodile/crocodilebruteforce.png)

I could see hidden directory, so lets check each one of them.

First lets check go for assets.

I could not get any information from the assets directory. lets check another one which is dashboard.

![p80tcphttp](/assets/img/crocodile/crocodilelogin.png)

This is what I got, a login form. Login as admin.

![p80tcphttp](/assets/img/crocodile/crocodileflag.png)

Finally I got the flag.

### Conclusion
This penetration test found security issue such as unauthorized ftp access and vulnerablity to http brute force attacks which helped in discovering flag. 