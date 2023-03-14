# SecDojo Web Lab 1

## General idea about the lab

this lab is a vulnerable web application designed to mimic a poorly designed e-banking solution. The application exposes typical e-banking functionalities: handling of account balance queries, bank statement downloads, bank transfers and many other functions that can help users customize their e-banking profile. These functions have not been designed with security in mind, there are many vulnerabilities to exploit.

> ### We use Nmap to see open ports and their services

![Alt text](Includes/1.png?raw=true "Title")

> ### Looking at the info above, we get assured that there is a web application running in an HTTP server; so we go to the application and register for a new account, after logging in with our account it appers that our account is not activited, but with looking at the request we notice something :

![Alt text](Includes/2.png?raw=true "Title")

> ### And that thing is that the cookie uses our username as the cookie, and because nothing is stopping us from changing it; we try doing so by changing the cookie `logged=hacker` to `logged=admin` just as follows:

![Alt text](Includes/3.png?raw=true "Title")

> ### And here looking at the response to the same request we found that there is a `URI` that allows us to download files; so we try our luck with this:

![Alt text](Includes/4.png?raw=true "Title")

> ### We will do that by triying to change the query :


![Alt text](Includes/5.png?raw=true "Title")

> ### So we change the query by a simple `LFI` payload :


![Alt text](Includes/6.png?raw=true "Title")

> ### As you see our payload worked so we should just get our proof that simply:


![Alt text](Includes/7.png?raw=true "Title")
