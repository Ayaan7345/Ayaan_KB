- #HTB
	- **CTF**
		- Recon
			- Nmap Scan
				- [nmapAutomator_10.10.11.230_Vulns.txt](../assets/nmapAutomator_10.10.11.230_Vulns_1694080007854_0.txt)
				- [nmapAutomator_10.10.11.230_Full.txt](../assets/nmapAutomator_10.10.11.230_Full_1694080033573_0.txt)
			- Fuff Scan
			- Nikto Scan
		- Web exploitation
			- The IP given redirects to http://cozyhosting.htb ![image.png](../assets/image_1694080130194_0.png)
			- Searching around the website found an interesting attack vector ![image.png](../assets/image_1694080216702_0.png)
			- Tried to grab the banner on the weird port 8083 didnt get anything ![image.png](../assets/image_1694080376268_0.png)
			- Leveraged searchsploit to see if there are common exploits ![image.png](../assets/image_1694080803800_0.png)
			- Tried to check for subdomains
			  ```
			  wfuzz -c -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u http://cozyhosting.htb -H "Host:FUZZ.cozyhosting.htb" --hc 200 -f ~/Documents/cozy/subdomaintest.txt
			  ```
			  [subdomaintest.txt](../assets/subdomaintest_1694082343278_0.txt)
			  the subdomain test didn't bear any fruits
			- found an error on the website
			  ![image.png](../assets/image_1694083838155_0.png)
			- After using dir search it found a useful directory this looks very promising 
			  ![image.png](../assets/image_1694498145218_0.png)
			- lets see if i can abuse cookies to get in
		- Privilege Escalation
		- Notes
			- Resources
			- Strategies
			- Other Notes