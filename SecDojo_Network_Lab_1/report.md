# SecDojo Network Lab 1

## General idea about the lab
The purpose of this lab is to learn how to perform network packet analysis in order to get more intel about the hidden network infrastructure, detect misconfigurations, and most importantly, how you can make use of this intel to get access to systems and escalate your privileges.

### First, we perform an nmap TCP scan to find the open and available ports and their services :
![Alt text](Includes/1.png?raw=true "Title")
### And another scan as UDP
![Alt text](Includes/2.png?raw=true "Title")
### We do a snmp check to gain more info about the network
![Alt text](Includes/3.png?raw=true "Title")
### After knocking on the ports we see that the ftp is now marked open not filtered as it once was
![Alt text](Includes/4.png?raw=true "Title")
### Using an nmap script we check if there is any data we can access as outsiders
![Alt text](Includes/5.png?raw=true "Title")
### After finding that there is a file we can access to anonymously , we login to ftp as an anonymous user and get the file
![Alt text](Includes/6.png?raw=true "Title")
![Alt text](Includes/7.png?raw=true "Title")
### in the file we see that we have http request and in it's body there is a username and a password we can use
![Alt text](Includes/8.png?raw=true "Title")
![Alt text](Includes/9.png?raw=true "Title")
![Alt text](Includes/10.png?raw=true "Title")
![Alt text](Includes/11.png?raw=true "Title")
![Alt text](Includes/12.png?raw=true "Title")
![Alt text](Includes/13.png?raw=true "Title")
![Alt text](Includes/14.png?raw=true "Title")
![Alt text](Includes/15.png?raw=true "Title")
![Alt text](Includes/16.png?raw=true "Title")