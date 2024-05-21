---
layout: post
title: Abusing COM objects
---

Yesterday I managed to complete the Fowsniff CTF room. It was quite simple and I highly reccomend it. Here I will talk about some of the things involved in that box.

1 - OSINT
The story is that the machine was hacked already and a hacker publically posted all the information, including hashed passwords and info that pop3 is wide open.
This doesn't really provide us with a realistic scenario but it's good for beginners.

2 - Passwords
On the Twitter page of the pwned company you will find a bunch of usernames and MD5 encoded hashes. I tried using John but it didn't work for some reason do I used a website instead.

3 - pop3d
Use Metasploit's pop3_login to bruteforce usernames and password combinations until you get it right. 

4 - More OSINT
You will get to a page with some emails sent, figure out what's the password for the SSH and what's the username (this one is a bit tricky so pay attention)

5 - SSH reverse shell
After getting into SSH, find a file that can be edited by the user and that has root previleges (hint: starting page picture)
After finding it, modify that file to run a reverse shell (just add the code, since it's a script after all). Then setup a netcat listener and restart the SSH.

6 - Done!
The last headache will be to find the flag in the folders.
