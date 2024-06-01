---
Title: SWS101 START UP
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![start up](../assets/startup/startup.png)

## Execute Summary


Target: 

## Information Gathering Phase

![nmap](../assets/startup/startupnmap.png)

Discovered 3 ports open.

![webpage](../assets/startup/startupweb.png)

Since port 80 is open, lets check it out hidden directories.

![hidden directories](../assets/startup/startuphiddendirectory.png)

I found a hidden directory. Lets check it out.

Wait!! Port 21 is open and lets check out whether we can login to ftp.

## Exploitation Phase

I am successfully logged in anoymously.  So I tried to upload revese shell file to get higher privilages and I was successful.

![ftp](../assets/startup/startupftplofin.png)

So lets execute the reverse shell file from searching from hidden directories.

I got the file that I uploaded from ftp in the hidden directory. Lets execute it.

![reverse shell](../assets/startup/startupfileupload.png)

![reverse shell](../assets/startup/startupreverseshell.png)

Now I got a reverse shell so lets upgrade it.

    python3 -c 'import pty; pty.spawn("/bin/bash")'

![shell upgrade](../assets/startup/startupshellupgrade.png)

After sneaking around I found the user called lennie and we don't have permission to get in.

In one of the directory called incident, there was a file `suspicious.pcapng` which I downloaded and checked it out. 


![suspicious.pcapng](../assets/startup/startuppcapngdef.png)

![pcapng open](../assets/startup/startuppcapngoen.png)

![wireshark](../assets/startup/startupwireshark.png)

There is a relationship between suspicous.pcapng and wireshare. Lets check it out.

I found a passowrd for lennie after analyzing the pcapng file using wireshark.

![lenniepassword](../assets/startup/startuplenniepassword.png)

So lets login to lennie using the password.

![lennie login](../assets/startup/startuplennielogin.png)

I found a user.txt.

![user.txt](../assets/startup/startupusertxt.png)

Comming soon...
