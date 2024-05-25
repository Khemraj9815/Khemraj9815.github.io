---
Title: SWS101 WGEL
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![wgel](../assets/wgel/wgel.png)


## Execute Summary

This pepetration test was held on the tryhackme machine "WGEL" with the primary objective of retrieving user.txt and root.txt.

Target: 10.10.84.92

## Information Gathering Phase

![nmap](../assets/wgel/wgelnmap.png)

Discovered 2 ports open.

![web](../assets/wgel/wgelweb.png)

This is what I got on wepage. Lets sneak out some information from here.

![jessie](../assets/wgel/wgeljessie.png)

I guess this is the username.

![ffuf](../assets/wgel/wgelffuff.png)

Got hidden directory. Lets check it out.

![idrsa](../assets/wgel/wgelidrsa.png)

Got id_rsa file. Lets try to crack it.

![no passwd](../assets/wgel/wgelnopasswd.png)

Then its making my work easier. Lets try to login with ssh.

Remember username is jessie.

## Exploitation Phase

![ssh](../assets/wgel/wgelssh.png)

Logged in successfully. Lets get the user.txt.

![user txt](../assets/wgel/wgelusertxt.png)

Got the user.txt. Lets move on to root.txt.







