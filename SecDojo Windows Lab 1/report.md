# SecDojo Windows Lab 1

## General idea about the lab

This lab is a network of vulnerable Windows servers. Each box suffers from a severe vulnerability that if properly exploited, will grant you administrator access and get you the root flag located at the Administrator desktop folder.

## First Box

### First, we perform an nmap scan to find the open and available ports and their services :
![Alt text](includes/1.png?raw=true "Title")
### -sV: Enables version detection, which will detect what versions are running on what port
### We found an http server and in it the following :
![Alt text](includes/2.png?raw=true "Title")
### I checked the sub folders of the directory and found the following :
![Alt text](includes/3.png?raw=true "Title")
### Then used pypkatz to extract the hashes from the dup file with the following cammand :
![Alt text](includes/4.png?raw=true "Title")
### Which led me to finding an NT hash for the adminstrator user :
![Alt text](includes/5.png?raw=true "Title")
### So I passed the Hash to wmiexec.py to grant me access to the Box :
![Alt text](includes/6.png?raw=true "Title")
### And now that I'am in, I just went to get the flag which was on the proof.txt :
![Alt text](includes/7.png?raw=true "Title")

## Second Box

### Same as before; we perform an nmap scan to find the open and available ports and their services :
![Alt text](includes/8.8.png?raw=true "Title")
### As you can see the port 445 is open, which led me to try and  list smb shares with these scripts that work with nmap , which I googled of course:
![Alt text](includes/9.png?raw=true "Title")
### As you can see, there was a Directory that was exposed to anonymous users and everyone has the right to raed, so I downloaded the files that we can extract the hives from them
![Alt text](includes/10.png?raw=true "Title")
### After downloading the files, I used secretsdump.py :
![Alt text](includes/11.png?raw=true "Title")
### So with psExec I gained access to the machine :
![Alt text](includes/12.png?raw=true "Title")

## Third Box

### Repetetion!!!
![Alt text](includes/13.1.png?raw=true "Title")
### In this Box, I was clueless what is the venurabily untel I got a hit about the it could be a vunerabilty in the netlogon which led me to zerologon exploit
![Alt text](includes/14.png?raw=true "Title")
### So I used the exploit to set the password to NULL
![Alt text](includes/15.png?raw=true "Title")
![Alt text](includes/16.png?raw=true "Title")
![Alt text](includes/17.png?raw=true "Title")

## Last Box

![Alt text](includes/19.png?raw=true "Title")
![Alt text](includes/20.png?raw=true "Title")
![Alt text](includes/21.png?raw=true "Title")
![Alt text](includes/22.png?raw=true "Title")