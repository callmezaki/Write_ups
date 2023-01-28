# SecDojo Windows Lab 2

## General idea about the lab

This lab serves as an environment to get you up and running with many aspects of Active Directory security. You will have access as a regular domain user and you will walk your way through all the misconfigurations in the domain environment. You are encouraged to detect as many vulnerabilities as you can. Some vulnerabilities will grant you Domain Admin access directly, others need to be combined to take over the domain. For this Lab you are given the following credentials: Username: LAB\student Password: hsxGs_72$

## Machine 1

### First, we perform a Nmap scan to find the open and available ports and their services :
![Alt text](Includes/1.png?raw=true "Title")

### From the scan we can conclude that this box is an Active directory, adding to the fact that we have an ordinary user account we escalate our privilege one way to do it is by abusing kerberoasting which is an extremely useful attack method to establish persistence, lateral movement, or privilege escalation in a Windows Active Directory environment. This attack is caused by a user requesting a TGS for an account, typically a service account, that has a Service Principal Name (SPN) associated with it. we could then use the TGS which is encrypted with the service account's NTLM password hash then crack it afterward and use it to gain access

### Using the command below we can find the SPNs that are tied to the user that we already have access to:
![Alt text](Includes/2.png?raw=true "Title")

### As you can see there is an SPN with a user account that's a member of Domain admins; with the same command but with an extra arg we can request a TGS :
![Alt text](Includes/3.png?raw=true "Title")

### After obtaining Hashed TGS we can crack it with hashcat as follows :

![Alt text](Includes/4.png?raw=true "Title")
![Alt text](Includes/5.png?raw=true "Title")
### Now  we can try to log in as that user using wmiexec:
![Alt text](Includes/6.png?raw=true "Title")
### Unfortunately, the login failed because the user password has expired, but we can renew it with smbpasswd command :
![Alt text](Includes/7.png?raw=true "Title")
### After renewing the password we try again and then that's it we are in we just should go grab the proof
![Alt text](Includes/8.png?raw=true "Title")
![Alt text](Includes/9.png?raw=true "Title")