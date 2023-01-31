# SecDojo Network Lab 2

## General idea about the lab 
The purpose of this lab is to show how an out-of-date network monitoring software can be exploited by an attacker to first obtain unprivileged access as 'apache' user and then exploit another vulnerability in the same network appliance to achieve root access.

### Same as always, we use Nmap to see open ports and their services :

![Alt text](Includes/1.png?raw=true "Title")

### After finding out that port 80 is open and there is apache server we go check it out :

![Alt text](Includes/2.png?raw=true "Title")

### We see that "Nagios xi" is running on the server so we can search for an exploit to try on it :

![Alt text](Includes/3.png?raw=true "Title")

### this Exploit can do the work for us; from gaining access as a regular user into escalating privilege to higher user :

![Alt text](Includes/4.png?raw=true "Title")



![Alt text](Includes/5.png?raw=true "Title")
![Alt text](Includes/6.png?raw=true "Title")
![Alt text](Includes/7.png?raw=true "Title")
