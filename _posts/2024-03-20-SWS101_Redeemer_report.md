---
Title: SWS101 Redeemer Report
categories: [SWS101,HACK THE BOX TIER_1]
tags: SWS 101
---

![redeemer](/assets/redeemer/redeeme.png)

## Executive Summary
In this penetration test, we explore Redeemer machine hosted on HACK THE BOX with the aim of accessing system security and our primary goal is to obtain flag. 

## Penetration Test Report

Target: 10.129.8.172

## Information Gathering Phase:
Port Scanning with Nmap:


        nmap -sV -T4 -p1-10000 10.129.8.172


![nmap](/assets/redeemer/redeemernmap.png)

Open ports discovered: 6379/tcp
Service version identified: Redis 5.0.7

![redis](/assets/redeemer/redis.png)


![redis cli](/assets/redeemer/rediscli.png)

### Enumerating Redis Server

![redis --help](/assets/redeemer/redishelp.png)


        redis-cli -h 10.129.8.172


![redis key](/assets/redeemer/rediskey.png)
  
Connected to redis server uaing redis-cli.

![key *](/assets/redeemer/redeemerlist.png)

### Exploitation Phase

![flag](/assets/redeemer/redeemerlist.png)

Got the flag!!!


        flag: 03e1d2b376c37ab3f5319922053953eb


### Conclusion 

This penetration test demonstrate our ability to get into the redis server to get the flag.