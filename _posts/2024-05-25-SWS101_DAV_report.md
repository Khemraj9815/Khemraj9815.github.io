---
Title: SWS101 DAV
categories: [SWS101,CTF Journal]
tags: SWS 101
---

![dav](../assets/dav/dav.jpeg)

## Execute Summary

This pepetration test was held on the tryhackme machine "DAV" with the primary objective of retrieving user.txt and root.txt.   


Target: 10.10.167.226

## Information Gathering Phase

![nmap](../assets/dav/davnmap.png)

Discovered 1 ports open.

![port 80](../assets/dav/davweb.png)

This is what I got on wepage. Lets sneak out some information from here.

![ffuf](../assets/dav/davffuf.png)

Got one hidden directory. Lets check it out.

![dav](../assets/dav/davwebdav.png)

![sign in](../assets/dav/davsignin.png)

![what](../assets/dav/davwhat.jpeg)

Lets find out the credentials for this.

![logn](../assets/dav/davlogin.png)

I got the credentials. Lets login.

## Exploitation Phase

![login success](../assets/dav/davloginsuccess.png)

![hash crack](../assets/dav/davhashcrack.png)

I tried to crack but I couldn't.

Lets find new way to exploit this.

Finally I found the exploit.

![exploit](../assets/dav/davexploitsearch.png)

![upload shell](../assets/dav/davuploadshell.png)

![upload command](../assets/dav/davuploadcommand.png)

I used same credentials to login from the terminal, it worked.

I could upload the reverse shell file.

![upload shell success](../assets/dav/davuploads.png)

Successfully uploaded the reverse shell file.

![file upload success](../assets/dav/davfileuploadsuccess.png)

![got a shell](../assets/dav/davgotashell.png)

Now lets stabilize the shell.

    python -c 'import pty; pty.spawn("/bin/bash")'

![stable shell](../assets/dav/davstableshell.png)

Let's sneak around to get the user flag.

![user flag](../assets/dav/davuserflag.png)

Got the user flag.

## Privilege Escalation Phase

Lets find the privilege escalation vector.

![cat](../assets/dav/davcat.png)

 I can run cat as root without password. Lets do this.

 ![root flag](../assets/dav/davrootflag.png)

Got the root flag.

## Final Thought

This was a fun machine. I learned about cadaver from this machine. I will try to do more machines like this. 

![yeah](../assets/dav/davyeah.jpeg)


