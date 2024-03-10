---
Title: SWS101 Flipped_class
categories: [SWS101,Flipped_1]
tags: SWS 101
---

# Topic: OverTheWire


### Summary

### Level 0
This level teaches how to use the shh (secure shell) command to get into another server.

### Level 1
While solving I knew how to use linux basic commands to navigate through the directory.

### Level 2
This is a new thing to me. If there is space in the name of the file, we have to use backslash(\) to see what is inside the file.

### Level 3
This level teaches a command to find hidden files in the directory.
Command to find hidden files:(ls -a)

### Level 4
At this level I learned a shortcut approach to check for human-readable files or any other specific file that we want to find. 

### Level 5
It was the same as level 4, but in this level we had to specify every detail of the file.

### Level 6
To find the password for the next level, we had to specify every detail of  the file that we were searching for.

### Level 7
I came across a new command called “grep”. This command is used to search through the file for the line containing a specific pattern.

### Level 8
At first I used “ iniq” command because the question says the character occur only once. Then I sorted all the characters(password for next level), I found many duplicates then I just counted the repetition of every character and there was a character with  no repetition and that was the password for next level.

### Level 9
It was just like level 7 where we use the “grep” command to search for a specific line of characters.


### Level 10
The password was enclosed with base64(designed to carry data stored in binary format). This level teaches how to decode the data given in base64.

### Level 11
To solve this I need the concept of rot13 which  means “a=n”, “b=p”, etc. After I found that the password was in the rot13 form then I used the “tr” command to make the password in normal form.

### Level 12
The main concept in this level is to know how to decompress the given file until it is in normal file.  

### Level 13
In this level we just had to login using sshkey.private file to another level.

### Level 14
This level teaches how to use netcat(nc) command to communicate with a server running on specific port on the local host.

### Level 15
It introduced to ssl command which is used to establish a secure connection to a server.

### Level 16
In this level, the main concept is to know how to use "nmap" to scan for open ports and identify the server running on specific ports, specifically focusing on services that use SSL encryption.

### Level 17
The password for next level was stored in paswords.new. The password is only the line that was changed between passwords.old and passwords.new. So I used "diff" command to find the password. 

### Level 18
To solve this level I needed to pass the modification in the ".bashrc" file. The pass work was stored in readme file in the home directory. Due to the ".bashrc" modification, I cannot directly access the file using simple "cat" command. Solution for this level is using "ssh" command with the "-t" option, which tells computer to acts as if it's real terminal.

### Level 19
This level is about using a special program that let us run commands as if I am another user. The program is called "bandit20-do". Normally, we can't read file that we don't have permission to read, but this program let us do that.

### Level 20
Again I faced the program called "suconnect", which is designed to connect to a specific port on my computer and then check if the password that I provide matches the previous level password. If the password is correct it send the password for next level.