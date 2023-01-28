# SecDojo Network Lab 1

## General idea about the lab
The purpose of this lab is to learn how to perform network packet analysis to get more intel about the hidden network infrastructure, detect misconfigurations, and most importantly, how you can make use of this intel to get access to systems and escalate your privileges.

### First, we perform a nmap TCP scan to find the open and available ports and their services :
![Alt text](Includes/1.png?raw=true "Title")
### And another scan as UDP
![Alt text](Includes/2.png?raw=true "Title")
### We do a nmap check to gain more info about the network
![Alt text](Includes/3.png?raw=true "Title")
### After knocking on the ports we see that the FTP is now marked open not filtered as it once was
![Alt text](Includes/4.png?raw=true "Title")
### Using n nmap script we check if there is any data we can access as outsiders
![Alt text](Includes/5.png?raw=true "Title")
### After finding that there is a file we can access anonymously, we log in to FTP as an anonymous user and get the file
![Alt text](Includes/6.png?raw=true "Title")
![Alt text](Includes/7.png?raw=true "Title")
### in the file, we see that we have an HTTP request and in its body, there is a username and a password we can use
![Alt text](Includes/8.png?raw=true "Title")
### we decode the password
![Alt text](Includes/9.png?raw=true "Title")
### And then use the credentials to log in using ssh
![Alt text](Includes/10.png?raw=true "Title")
### after we gained access we should find a way to elevate our privilege; when executing the command "sudo -l", it tells you what can you do without a password, in our case we can execute "Wget" with high privilege without the need of being soduers ?Forgot to screenshot it?
### With that info, I sent the /etc/shadow file to my local machine and changed the root hash to be the same hash of the user that I already know the password of, and then I posted it back, so I can log in to root
![Alt text](Includes/11.png?raw=true "Title")
![Alt text](Includes/12.png?raw=true "Title")
![Alt text](Includes/13.png?raw=true "Title")
![Alt text](Includes/14.png?raw=true "Title")
![Alt text](Includes/15.png?raw=true "Title")
![Alt text](Includes/16.png?raw=true "Title")