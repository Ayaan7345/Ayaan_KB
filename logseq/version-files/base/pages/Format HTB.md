- #HTB
	- **CTF**
		- Recon
			- Nmap Scan
			- Fuff Scan
			- Nikto Scan
		- Web exploitation
		- Privilege Escalation
		- Notes
			- Resources
			- Strategies
				- Recon
					- Didnt get much out of a Nmap scan had these ports open 
					  ```
					  PORT     STATE SERVICE
					  22/tcp   open  ssh
					  80/tcp   open  http
					  3000/tcp open  ppp
					  ```
					- so i tried to find subdomains for microblog.htb didnt find anything
					- ```
					  ┌──(kali㉿redteam)-[~/Documents/format]
					  └─$ ffuf -w /usr/share/wordlists/wfuzz/general/big.txt -u http://FUZZ.microblog.htb 
					  
					          /'___\  /'___\           /'___\       
					         /\ \__/ /\ \__/  __  __  /\ \__/       
					         \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
					          \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
					           \ \_\   \ \_\  \ \____/  \ \_\       
					            \/_/    \/_/   \/___/    \/_/       
					  
					         v2.0.0-dev
					  ________________________________________________
					  
					   :: Method           : GET
					   :: URL              : http://FUZZ.microblog.htb
					   :: Wordlist         : FUZZ: /usr/share/wordlists/wfuzz/general/big.txt
					   :: Follow redirects : false
					   :: Calibration      : false
					   :: Timeout          : 10
					   :: Threads          : 40
					   :: Matcher          : Response status: 200,204,301,302,307,401,403,405,500
					  ________________________________________________
					  
					  [Status: 200, Size: 3976, Words: 899, Lines: 84, Duration: 38ms]
					      * FUZZ: app
					  
					  :: Progress: [3024/3024] :: Job [1/1] :: 578 req/sec :: Duration: [0:00:05] :: Errors: 3023 ::
					  
					  ```
					- So then I tried to grab the banner off of port 3000
					  ```
					  ┌──(kali㉿redteam)-[~/Documents/format]
					  └─$ nc -nv 10.10.11.213 3000                                                                                      1 ⨯
					  (UNKNOWN) [10.10.11.213] 3000 (?) open
					  
					  ls
					  HTTP/1.1 400 Bad Request
					  Server: nginx/1.18.0
					  Date: Mon, 04 Sep 2023 23:39:17 GMT
					  Content-Type: text/html
					  Content-Length: 157
					  Connection: close
					  
					  <html>
					  <head><title>400 Bad Request</title></head>
					  <body>
					  <center><h1>400 Bad Request</h1></center>
					  <hr><center>nginx/1.18.0</center>
					  </body>
					  </html>
					               ```
					- It looks like this is an api that I could probably abuse
					- I was wrong its another web page
					- ![image.png](../assets/image_1693871597045_0.png)
					-
			- Other Notes
				- Potential user Cooper
-