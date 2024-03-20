---
Title: SWS101 Sequel Report
categories: [SWS101,HACK THE BOX TIER_1]
tags: SWS 101
---
![sequel](/assets/img/sequel.png)

## Executive Summary
In this penetraiton test, we explore Sequel machine with the aim of checking system secirity and our primary goal is is to obtain the flag.

## Penetration Test Report
Target: 10.129.253.86

## Information Gathering Phase:
Port Scanning with Nmap:

        nmap -T4 -F -oN initial_scan


- -T4: scan faster with less detail.
- -F: checks for most common ports.
-  -oN initial_scan: it save the scaned result to a file named initial_scan.

![nmap](/assets/img/sequelnmap.png)

Target machine has port 3306 open, which is default port used by MySQL.

### Servise scan:
        nmap -sS -sV -sC -p 3306 --max-retries 2 --max-scan-delay 50ms --open -n -v -oN service_scan 10.129.95.232

- -sS: checks the status of port 3306 without connecting it fully.
- -sV: find what services is running on port 3306.
- -sC: ask nmap to scan more detailly on the services running on port 3306.
-  --max-retries 2: it attempts just 2 times to connect.
- --max-scan-delay 50ms: wait 50miliseconds before attempting another time.
- --open: just show the open ports.
- -n: ship looking for hostname.
- -v: it gives detailed output.

![service scan](/assets/img/servicescansequel.png)

Servise scan reveals that port 3306 is running MariaDB version 10.3.27.

### MySQL Enumeration

        mysql --help   

![mysql](/assets/img/sequelhost.png)
![mysql](/assets/img/sequeluser.png)

It's time to Google.

![mysql](/assets/img/sequelmariagoogle.png)
![mysql](/assets/img/sequelmariaroot.png)

We can login into MariaDB without providing password using root privilege.

So lets try to login into MariaDB using root user.

        mysql -h 10.129.95.232 -u root 

- -h : Connect to host.
- -u : User for log-in if not current user.

![mysql](/assets/img/sequelmariadblogin.png)

I could login using root user.

Now we can explore the tables and data that are available.

### Exploitation Phase

![mysql](/assets/img/sequelshowdata.png)

let's try this command.

        SHOW databases;

![mysql](/assets/img/sequeldatabase.png)

Let's get into the database and retrive the flag.

        use <database_name>

![sequel database](/assets/img/sequelusedatabase.png)

![mysql](/assets/img/sequelhtb.png)

let's see what is in the htb database.
![htb table](/assets/img/sequelhtbtable.png)

Now let's see what is there in the config table.

![table](/assets/img/sequelcongiftable.png)

`        SELECT * FROM <table_name>

`![flag](/assets/img/sequelflag.png)

        flag: 7b4bec00d1a39e3dd4e021ec3d915da8
This is what we want!!!

### Conclusion
This penetration test demonstrated our ability to exploit misconfigured MySQL database to retrive sensitive information.
