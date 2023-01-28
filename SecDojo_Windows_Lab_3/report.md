# SecDojo Windows Lab 3

## General idea about the lab

This lab contains two Microsoft Windows machines. To achieve access and obtain the Flags, you will have to conduct an SMB relay attack on those machines. One of those machines contains some SCF files. Learn how to use SCF files to grab juicy pieces of information.

## Machine 1

### As always, we perform n Nmap scan to find the open and available ports and their services :
![Alt text](Includes/1.png?raw=true "Title")
### And for an attempt to find some SCF files in the SMB shares because I found port 445 open; I used the scripts to list the SMB shares :

![Alt text](Includes/2.png?raw=true "Title")


# Now we start performing a SMB relay attack