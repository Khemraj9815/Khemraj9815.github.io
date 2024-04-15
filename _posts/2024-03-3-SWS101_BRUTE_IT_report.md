---
Title: SWS101 BRUTE IT
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![brute it](../assets/bruteit/btuteit.png)

### Executive Summary

This pepetration test was held on the tryhackme machine "Brute it" with the primary objective of escalating privilege and retrieving user.txt and root.txt.   

### Information Gathering Phase

Target: 10.10.155.162

Nmap Scan:

    nmap -sC -sV -Pn 10.10.155.162

![nmap](../assets/bruteit/brutenmap.png)

this is what is got

![web page](../assets/bruteit/btutewebpage.png)

Lets see the hidden dir

![gobuster](../assets/bruteit/gobuster.png)

Navigate to /admin

![login page](../assets/bruteit/brutelogin.png)

I don't have any clue what what are username and password.

let's break it using hydra

ohh user name is "admin"
![username](../assets/bruteit/usernameadmin.png)

![hydra](../assets/bruteit/hydra.png)

![how to use hydra](../assets/bruteit/howtousehydra.png)

![hydra applyed](../assets/bruteit/hydraapply.png)

Got password for admin!!!
![web pass](../assets/bruteit/webpass.png)

![admin webpage](../assets/bruteit/rsaprivatekey.png)

![rsa pk](../assets/bruteit/rsapk.png)

![what](../assets/bruteit/what.gif)

![five hours later](../assets/bruteit/hours.gif)

finally I got the solution to crack the hash.

 go to this [link](https://www.onlinehashcrack.com/tools-private-key-ssh-rsa-dsa-openssh-hash-extractor.php) and convert rsa_id to hash.

    $ john rockyou.txt <name of file which has hash.txt>

   
![john](../assets/bruteit/john.png)

Though I got the solution but due to poor condition of my laptop I could not crack the hash.

![ssh](../assets/bruteit/sshrsa.png)

lets Go...


### Enumeration Phase

![enumeration](../assets/bruteit/enumeration.png)

I was able to login successfully.

Now find user.txt

### Privilege Escalation

![root hash](../assets/bruteit/rootpass.png)

I got the hash for root user.


let's crack it!!!

![crack root hash](../assets/bruteit/rootpwd.png)

![root flag](../assets/bruteit/rootflag.png)


![yeah](../assets/bruteit/yeah.gif)

### Final Thought

It is  interestinig room for begineer, it let us to use new tools like hydra which has unique and it was easy to use. It also introduce to new tool 'john', which I never heard about it.




