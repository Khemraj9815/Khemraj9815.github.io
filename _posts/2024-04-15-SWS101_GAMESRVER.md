---
Title: SWS101 GAMESERVER
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![game server](../assets/gameserver/gameserver.jpeg)

## Penetration Test Report

Target: 10.10.125.125

### Information Gathering Phase

Port Scanning with Nmap:

    nmap -sV -vv -sC 10.10.125.125


![nmap](../assets/gameserver/gameserverport.png)

![game server nmap](../assets/gameserver/gameservernmap.png)

Discovered 2 ports open.

![port 22](../assets/gameserver/gameserverport22.png)

Lets go for port 80.

![port 80](../assets/gameserver/gameserverwebpage.png)

This is what I got on wepage. Lets sneak out some information from here.

assets/gameserver/gameserverusername.png

![user name](../assets/gameserver/gameserverusername.png)

Haha! I guess this is the username. I couldn't find any important information here. Lets try to brute force the hidden directories.

For brute forcing, am gonna use ffuf. 

![ffuf](../assets/gameserver/gameserverffuf.png)

![ffuf result](../assets/gameserver/gameserverffufresult.png)

Those are the hidden directories. Lets check one by one. First of all lets go for secret because its seems somthing is there.

![rsa private key](../assets/gameserver/gameserverrsakey.png)

This is second time I am dealing with rsa private key.

![ssh](../assets/gameserver/gameserverssh.png)

Now I have to crack the rsa key to get the password. Lets do this!!!

![rsa hash](../assets/gameserver/gameserverrsahash.png)

I got the hash for rsa key.

Lets crack it!!

assets/gameserver/gameserverhachcrasked.png

![hash cat](../assets/gameserver/gameserverhashcat.png)

![hash cracked](../assets/gameserver/gameserverhachcrasked.png)

![hash password](../assets/gameserver/gameserverhashpass.png)

![yeah](../assets/gameserver/gameserveryeah.gif)


Now I have both password and username. Lets login to ssh.



