---
layout: post
title: Abusing COM objects
---

Nmap is an awesome tool to research a target and find ways to attack it. If you're just getting into hacking, there might be some functionalities in nmap that you don't know about.



Netmap overview:
The main functionality of nmap is to scan for open ports and find out more about these ports. Knowing which ports are open is crucial because that's how you get into a network.



1- TCP / UDP / SYN


There are 3 ways to scan ports with nmap, and they do different things.

TCP:
TCP is a protocol in which, to establish a connection, the client sends a synchronization request to the server, then the server returns a sync-acknowledgment back to the client and then the client sends another acknowledgment request. Think about a computer and a server, the computer says "do you hear me?", the server says "yes, just confirm that you can hear me too" and the computer says "I do" (3 ways). The whole point of TCP is to make sure that the client and the server can reach each other before sending stuff.
Nmap allows you to use tcp to scan for ports. The same thing happens: you talk to the server, it replies and you reply back. (If we don't reply at the end, it's because the server will just keep sending us a request). If there is a firewall, it send no response, so we will know that the port is filtered (when they are closed, we get a "port closed" back)
To do a TCP scan, use the -sT flag. Ex:    nmap -sT 123.456.89.111     A TCP scan is done automatically if you're not using sudo.

UDP:
In his protocol, we just bombard the server with packets. In networking, this is more often used when speed is a priority (like when you're in a zoom call and the image gets pixelated) because we don't make sure that all files get there. You would expect this to be faster, but it's actually slower than using TCP with nmap because nmap will send packets and double check it and hope that the service that works in that port has some specific answer it has to send (ex: FTP will ask you to login). We can't know if the port is using a firewall or is just closed. 
Use the -sU flag, ex:      nmap -sU 123.456.78.876

SYN:
This is a modification of TCP in which instead of the client sending a final acknowledgment, we send a cancel request. This makes SYN a lot faster because we do not need to fully establish connections and then break them.
Use the -sS flag.
