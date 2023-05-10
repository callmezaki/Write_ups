# SecDojo Windows Lab 1

## General idea about the lab

This lab is a network of vulnerable Windows servers. Each box suffers from a severe vulnerability that if properly exploited, will grant you administrator access and get you the root flag located in the Administrator desktop folder.

## First Machine

> ### First, we perform n nmap scan to find the open and available ports and their services :

![Alt text](includes/1.png?raw=true "Title")

> ### -sV: Enables version detection, which will detect what versions are running on what port

> ### We found an HTTP server and in it the following :

![Alt text](includes/2.png?raw=true "Title")

### I checked the subfolders of the directory and found the following :

![Alt text](includes/3.png?raw=true "Title")

> ### Then used pypkatz to extract the hashes from the dup file with the following command :

![Alt text](includes/4.png?raw=true "Title")

> ### Which led me to find an NT hash for the administrator user :

![Alt text](includes/5.png?raw=true "Title")

> ### So I passed the Hash to wmiexec.py to grant me access to the Machine :

![Alt text](includes/6.png?raw=true "Title")

> ### And now that I am in, I just went to get the flag which was on the proof.txt :

![Alt text](includes/7.png?raw=true "Title")

## Second Machine

> ### Same as before; we perform a Nmap scan to find the open and available ports and their services :

![Alt text](includes/8.8.png?raw=true "Title")

> ### As you can see port 445 is open, which led me to try and  list SMB shares with these scripts that work with Nmap, which I googled of course:

![Alt text](includes/9.png?raw=true "Title")

> ### As you can see, there was a Directory that was exposed to anonymous users and everyone has the right to read, so I downloaded the files so that we can extract the hives from them

![Alt text](includes/10.png?raw=true "Title")

> ### After downloading the files, I used secretsdump.py :

![Alt text](includes/11.png?raw=true "Title")

> ### So with psExec, I gained access to the machine :

![Alt text](includes/12.png?raw=true "Title")

## Third Machine

### Repetition!!!

![Alt text](includes/13.1.png?raw=true "Title")

### In this Machine, I was clueless about what is the venerability until I got a hit that says it could be a vulnerability in the netlogon which led me to zero-logon exploit

![Alt text](includes/14.png?raw=true "Title")

### So I used the exploit to set the password to NULL

![Alt text](includes/15.png?raw=true "Title")

### After that I used, secret-dump again to gain access

![Alt text](includes/16.png?raw=true "Title")

### And now that I am in, I just went to get the flag which was on the proof.txt :

![Alt text](includes/17.png?raw=true "Title")

## Last Machine

### So you know that I'm a newbie at this I forgot to screenshot the Nmap output, but it's okay;  I found that port 80 is open so I checked the website:

![Alt text](includes/19.png?raw=true "Title")

### I found that it has HFS service, so I just searched if there is an exploit that I can use, And Viola:

![Alt text](includes/20.png?raw=true "Title")

### then set the value with my data :

![Alt text](includes/21.png?raw=true "Title")

### and as you can see I gained Access to the Machine:

![Alt text](includes/22.png?raw=true "Title")
