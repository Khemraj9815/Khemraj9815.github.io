---
Title: SWS101 OWASP TOP 10
categories: [SWS101,UNIT 3]
tags: SWS 101
---

![sequel](../assets/owasp/owasp.jpeg)

### 1. Broken Access Control

Only the site's admin user are able to access the procted page, if normal user are able to access them then access controls are broken. 

If access control are broken:
* normal user will be able to view sensitive data.
* Unthorized access control.

![user platform](../assets/owasp/acces2.png)

Unthorized access control

![broken access](../assets/owasp/acces1.png)

This occurs when an application provides direct access to objects based on user-supplied input. As a result attacker and  bypass authorization and access sensitive data.

### 2. Cryptographic Failures

Cryptographic Failures arises from misuse (or lack of use) of cryptographic algorithms for protecting sensitive information.

Communication between server and client should be encrypted so that no one can see the conversation between server and client.

Communications between server and client are encrypted.

![cryptographic](../assets/owasp/cryptography.png)

 Cryptographic Failures

![cryptography fail](../assets/owasp/cryptographicfail.png)

### 3. Injection

SQL injection occurs when attacker inserts malicious SQL code into query, which have potential to manipulate the database and  can access the sensitive information.

![sql injection attack](../assets/owasp/sqlinjectionattack.png)

Command injection happens when a application doesn't take the user input to system shell without sanitizing. Attacker can just issue command and do what ever they want as if they are sitting infront of server.

![sql injection attack](../assets/owasp/commandinjection.png)


### 4. Insecure Design

Its a application that is build without thinking about the security. So there could be weak points for attacker to get unauthorized access.

![insecure design](../assets/owasp/insecuredesign.png)


### 5. Security Misconfiguration

Security Misconfiguration happens when the system are not setup correctly which creates vulnerabilities that can be exploited by attacker.

Security Misconfiguration can leads to unauthorized access to sensitive data. 


Security misconfigurations include:

* Default accounts with unchanged passwords.
* enabling unnecessary feature on.
* Not using HTTP security headers.

![security misconfiguration](../assets/owasp/securitymis.png)


### 6. Vulnerable and Outdated Components

![Vulnerable](../assets/owasp/outdate.png)


![Vulnerable](../assets/owasp/Vulnerable.png)

Coming soon..









