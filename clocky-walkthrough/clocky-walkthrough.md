#tryhack me clocky walthrough

#machine name: CLOCKY
#difficulty: MEDIUM
#category: 


first we scan the target machine using NMAP

-> nmap -sV -sC -A -T4 $ip 

->the result gotten after the scan:
![alt text](<nmap scan-1.png>)

OPEN PORTS
----------
[80]->http 
[22]->ssh
[8080]->http-proxy
[8000]-> http


as you can see 'http" service is open. less try to check the website hosted.
![alt text](<webpage view 1-1.png>)

nothing interesting found on the website i would say. but let's find out if it has robots file:
run -> http://$ip:8000/robots.txt
 
 ![alt text](<flag 1-1.png>)

 and BINGO!🥳.
 



