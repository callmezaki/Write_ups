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
### 
![Alt text](includes/7.png?raw=true "Title")
![Alt text](includes/8.8.png?raw=true "Title")
![Alt text](includes/9.png?raw=true "Title")
![Alt text](includes/10.png?raw=true "Title")
![Alt text](includes/11.png?raw=true "Title")
![Alt text](includes/12.png?raw=true "Title")
![Alt text](includes/13.1.png?raw=true "Title")
![Alt text](includes/14.png?raw=true "Title")
![Alt text](includes/15.png?raw=true "Title")
![Alt text](includes/16.png?raw=true "Title")
![Alt text](includes/17.png?raw=true "Title")
![Alt text](includes/18.png?raw=true "Title")
![Alt text](includes/19.png?raw=true "Title")
![Alt text](includes/20.png?raw=true "Title")
![Alt text](includes/21.png?raw=true "Title")
![Alt text](includes/22.png?raw=true "Title")