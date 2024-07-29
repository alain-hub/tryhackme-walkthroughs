TRYHACKME WALKTHROUGH
-------------------------

->machine name: CLOCKY

->difficulty: MEDIUM


->category: WEB-SERVER


first we scan the target machine using NMAP

-> nmap -sV -sC -A -T4 $ip 

->the result gotten after the scan:
![alt text](<nmap scan-1.png>)

OPEN PORTS
----------
->[80]->http 

->[22]->ssh

->[8080]->http-proxy


->[8000]-> http


as you can see 'http" service is open. less try to check the website hosted.


![alt text](<webpage view 1-1.png>)

nothing interesting found on the website i would say. but let's find out if it has robots file:


run -> http://$ip:8000/robots.txt
 
 ![alt text](<flag 1-1.png>)

 and BINGO!🥳.
 
 let's also check if there are other interesting directories using dirbuster

 -> gobuster dir -u http://$ip:8000 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -t 50 


after some directory scrapping through, i got across an interesting directory: 
![alt text](<index zip 2-1.png>)

after accessing, it automatically downloads itself. it appears to be a zipped file. i unzip it and it contains two files:

1. app.py
2. flag2.txt

by using,

-> cat flag2.txt

we have found our flag 2 ladies and gentlemen!

![alt text](<flag 2-1.png>)


now onto flag 3 hunt!

let's dive into the "app.py script" to see if we can get something interesting.





