# htb-beep
This is my Hack the box's Beep machine write-up.

## Machine

OS: GNU/Linux

IP: 10.10.10.7

Difficulty: Easy


## Initial enumeration
[Nmap](https://github.com/nmap/nmap) scan on the target:

`nmap -sV -sC -oN beep.nmap $BEEP`

Flags:
 - `-sV`: Version detection
 - `-sC`: Script scan using the default set of scripts
 - `-oN`: Output in normal nmap format
 
 ```
Starting Nmap 7.80 ( https://nmap.org ) at 2020-06-26 18:07 EDT
Nmap scan report for 10.10.10.7
Host is up (0.016s latency).
Not shown: 988 closed ports
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 4.3 (protocol 2.0)
25/tcp    open  smtp       Postfix smtpd
|_smtp-commands: Couldn't establish connection on port 25
80/tcp    open  http       Apache httpd 2.2.3
110/tcp   open  pop3       Cyrus pop3d 2.3.7-Invoca-RPM-2.3.7-7.el5_6.4
111/tcp   open  rpcbind
143/tcp   open  imap       Cyrus imapd 2.3.7-Invoca-RPM-2.3.7-7.el5_6.4
443/tcp   open  ssl/https?
993/tcp   open  ssl/imap   Cyrus imapd
995/tcp   open  pop3       Cyrus pop3d
3306/tcp  open  mysql      MySQL (unauthorized)                                                                                                                                  
4445/tcp  open  upnotifyp?                                                                                                                                                       
10000/tcp open  http       MiniServ 1.570 (Webmin httpd)                                                                                                                         
Service Info: Hosts:  beep.localdomain, 127.0.0.1, example.com                                                                                                                   

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 452.97 seconds
```
