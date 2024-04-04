---
Title: SWS101 BRUTE IT
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![alt text](../assets/bruteit/btuteit.png)


Nmap Scan:

    nmap -sC -sV -Pn 10.10.155.162

![nmap](../assets/bruteit/brutenmap.png)

    PORT   STATE SERVICE VERSION
    22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
    | ssh-hostkey: 
    |   2048 4b:0e:bf:14:fa:54:b3:5c:44:15:ed:b2:5d:a0:ac:8f (RSA)
    |   256 d0:3a:81:55:13:5e:87:0c:e8:52:1e:cf:44:e0:3a:54 (ECDSA)
    |_  256 da:ce:79:e0:45:eb:17:25:ef:62:ac:98:f0:cf:bb:04 (ED25519)
    80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
    |_http-server-header: Apache/2.4.29 (Ubuntu)
    |_http-title: Apache2 Ubuntu Default Page: It works
    Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel


this is what is got
![web page](../assets/bruteit/btutewebpage.png)

Lets see the hidden dir

![gobuster](../assets/bruteit/gobuster.png)

Navigate to /admin

![login page](../assets/bruteit/brutelogin.png)

I don't have any clue what what are username and password.

let's break it using hydra

user name is "admin"
![username](../assets/bruteit/usernameadmin.png)

![hydra](../assets/bruteit/hydra.png)

![how to use hydra](../assets/bruteit/howtousehydra.png)

![hydra applyed](../assets/bruteit/hydraapply.png)

Got password for admin!!!
![web pass](../assets/bruteit/webpass.png)

![admin webpage](../assets/bruteit/rsaprivatekey.png)

![rsa pk](../assets/bruteit/rsapk.png)

![what](../assets/bruteit/what.gif)


Work in progress



