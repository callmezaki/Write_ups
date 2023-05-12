# SecDojo Linux Lab 1

## General idea about the lab

> `The purpose of this lab is to reveal how SSH misconfigurations can be abused to gain access to a remote machine, elevate privileges, and perform pivoting. The lab is composed of 2 machines, on each machine, you have to gain unprivileged access first (1st Flag), then achieve root access (2nd Flag). The two machines are linked.`

## First Machine

> To begin, we initiate the enumeration phase by performing an Nmap scan: `nmap -sV -Pn -T4` :

![Alt text](Includes/1.png?raw=true)

> The scan reveals that the machine is running an Apache server with an HTTP service, but no significant findings are observed:

![Alt text](Includes/2.png?raw=true)

> However, upon using the "dirb" or "dirbuster" command to scan for directories, we discover a robots.txt file that leads us to a directory containing a WordPress web application, which does not provide any useful information:

![Alt text](Includes/3.png?raw=true)

> Since the previous lead is a dead end, we proceed with enumerating SSH users using the  `ssh_enumusers` exploit in Metasploit:

![Alt text](Includes/4.png?raw=true)

> We specify the host IP and provide a wordlist for the exploit to run:

![Alt text](Includes/5.png?raw=true)

> The exploit successfully runs, and we obtain a list of users. Next, we need to identify real users, excluding default or service accounts:

![Alt text](Includes/6.png?raw=true)

> We find a user named "user" and attempt to authenticate via SSH using "user" as both the username and password:

![Alt text](Includes/7.png?raw=true)

> As shown, the login is successful, granting us initial access to the machine and allowing us to retrieve the flag:

![Alt text](Includes/8.png?raw=true)

> Previlage escalation was simple because we have access to the root folder and our user is the owner of the .ssh folder:

![Alt text](Includes/9.png?raw=true)

> Now I just add my ssh public key to the `authorized_keys` file in .ssh folder and change the permissions to the default ones of the file:

![Alt text](Includes/10.png?raw=true)
![Alt text](Includes/11.png?raw=true)

> We are in :

![Alt text](Includes/12.png?raw=true)

## Second machine

> Considering the interconnected nature of the two machines, we need to find a way to connect to the second machine through the first one. Upon investigation, we discover that the user we previously logged in with has a known_hosts file. Interestingly, the IP mentioned in the file corresponds to the second machine. We proceed to log in using this information:

![Alt text](Includes/13.png?raw=true)
