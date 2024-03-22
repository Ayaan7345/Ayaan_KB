- Enumeration Cheat Sheets
  collapsed:: true
	- ## Infrastructure-based Enumeration
	  
	  |**Command**|**Description**|
	  |-|-|
	  | `curl -s https://crt.sh/\?q\=<target-domain>\&output\=json \| jq .` | Certificate transparency. |
	  | `for i in $(cat ip-addresses.txt);do shodan host $i;done` | Scan each IP address in a list using Shodan. |
	  
	  ----
	- ## Host-based Enumeration
	- ##### FTP
	  |**Command**|**Description**|
	  |-|-|
	  | `ftp <FQDN/IP>` | Interact with the FTP service on the target. |
	  | `nc -nv <FQDN/IP> 21` | Interact with the FTP service on the target. |
	  | `telnet <FQDN/IP> 21` | Interact with the FTP service on the target. |
	  | `openssl s_client -connect <FQDN/IP>:21 -starttls ftp` | Interact with the FTP service on the target using encrypted connection. |
	  | `wget -m --no-passive ftp://anonymous:anonymous@<target>` | Download all available files on the target FTP server. |
	- ##### SMB
	  |**Command**|**Description**|
	  |-|-|
	  | `smbclient -N -L //<FQDN/IP>` | Null session authentication on SMB. |
	  | `smbclient //<FQDN/IP>/<share>` | Connect to a specific SMB share. |
	  | `rpcclient -U "" <FQDN/IP>` | Interaction with the target using RPC. |
	  | `samrdump.py <FQDN/IP>` | Username enumeration using Impacket scripts. |
	  | `smbmap -H <FQDN/IP>` | Enumerating SMB shares. |
	  | `crackmapexec smb <FQDN/IP> --shares -u '' -p ''` | Enumerating SMB shares using null session authentication. |
	  | `enum4linux-ng.py <FQDN/IP> -A` | SMB enumeration using enum4linux. |
	- ##### NFS
	  |**Command**|**Description**|
	  |-|-|
	  | `showmount -e <FQDN/IP>` | Show available NFS shares. |
	  | `mount -t nfs <FQDN/IP>:/<share> ./target-NFS/ -o nolock` | Mount the specific NFS share.umount ./target-NFS |
	  | `umount ./target-NFS` | Unmount the specific NFS share. |
	- ##### DNS
	  |**Command**|**Description**|
	  |-|-|
	  | `dig ns <domain.tld> @<nameserver>` | NS request to the specific nameserver. |
	  | `dig any <domain.tld> @<nameserver>` | ANY request to the specific nameserver. |
	  | `dig axfr <domain.tld> @<nameserver>` | AXFR request to the specific nameserver. |
	  | `dnsenum --dnsserver <nameserver> --enum -p 0 -s 0 -o found_subdomains.txt -f ~/subdomains.list <domain.tld>` | Subdomain brute forcing. |
	- ##### SMTP
	  |**Command**|**Description**|
	  |-|-|
	  | `telnet <FQDN/IP> 25` |  |
	- ##### IMAP/POP3
	  |**Command**|**Description**|
	  |-|-|
	  | `curl -k 'imaps://<FQDN/IP>' --user <user>:<password>` | Log in to the IMAPS service using cURL. |
	  | `openssl s_client -connect <FQDN/IP>:imaps` | Connect to the IMAPS service. |
	  | `openssl s_client -connect <FQDN/IP>:pop3s` | Connect to the POP3s service. |
	- ##### SNMP
	  |**Command**|**Description**|
	  |-|-|
	  | `snmpwalk -v2c -c <community string> <FQDN/IP>` | Querying OIDs using snmpwalk. |
	  | `onesixtyone -c community-strings.list <FQDN/IP>` | Bruteforcing community strings of the SNMP service. |
	  | `braa <community string>@<FQDN/IP>:.1.*` | Bruteforcing SNMP service OIDs. |
	- ##### MySQL
	  |**Command**|**Description**|
	  |-|-|
	  | `mysql -u <user> -p<password> -h <FQDN/IP>` | Login to the MySQL server. |
	- ##### MSSQL
	  |**Command**|**Description**|
	  |-|-|
	  | `mssqlclient.py <user>@<FQDN/IP> -windows-auth` | Log in to the MSSQL server using Windows authentication. |
	- ##### IPMI
	  |**Command**|**Description**|
	  |-|-|
	  | `msf6 auxiliary(scanner/ipmi/ipmi_version)` | IPMI version detection. |
	  | `msf6 auxiliary(scanner/ipmi/ipmi_dumphashes)` | Dump IPMI hashes. |
	- ##### Linux Remote Management
	  |**Command**|**Description**|
	  |-|-|
	  | `ssh-audit.py <FQDN/IP>` | Remote security audit against the target SSH service. |
	  | `ssh <user>@<FQDN/IP>` | Log in to the SSH server using the SSH client. |
	  | `ssh -i private.key <user>@<FQDN/IP>` | Log in to the SSH server using private key. |
	  | `ssh <user>@<FQDN/IP> -o PreferredAuthentications=password` | Enforce password-based authentication. |
	- ##### Windows Remote Management
	  |**Command**|**Description**|
	  |-|-|
	  | `rdp-sec-check.pl <FQDN/IP>` | Check the security settings of the RDP service. |
	  | `xfreerdp /u:<user> /p:"<password>" /v:<FQDN/IP>` | Log in to the RDP server from Linux. |
	  | `evil-winrm -i <FQDN/IP> -u <user> -p <password>` | Log in to the WinRM server. |
	  | `wmiexec.py <user>:"<password>"@<FQDN/IP> "<system command>"` | Execute command using the WMI service. |
	- ##### Oracle TNS
	  |**Command**|**Description**|
	  |-|-|
	  | `./odat.py all -s <FQDN/IP>` | Perform a variety of scans to gather information about the Oracle database services and its components. |
	  | `sqlplus <user>/<pass>@<FQDN/IP>/<db>` | Log in to the Oracle database. |
	  | `./odat.py utlfile -s <FQDN/IP> -d <db> -U <user> -P <pass> --sysdba --putFile C:\\insert\\path file.txt ./file.txt` | Upload a file with Oracle RDBMS. |
- What is Enumeration
	- What can we see?
	  What reasons can we have for seeing it?
	  What image does what we see create for us?
	  What do we gain from it?
	  How can we use it?
	  What can we not see?
	  What reasons can there be that we do not see?
	  What image results for us from what we do not see?
		- that
- Enumeration methodology
	- | **Layer** | **Description** | **Information Categories** |
	  | ---- | ---- | ---- |
	  | `1. Internet Presence` | Identification of internet presence and externally accessible infrastructure. | Domains, Subdomains, vHosts, ASN, Netblocks, IP Addresses, Cloud Instances, Security Measures |
	  | `2. Gateway` | Identify the possible security measures to protect the company's external and internal infrastructure. | Firewalls, DMZ, IPS/IDS, EDR, Proxies, NAC, Network Segmentation, VPN, Cloudflare |
	  | `3. Accessible Services` | Identify accessible interfaces and services that are hosted externally or internally. | Service Type, Functionality, Configuration, Port, Version, Interface |
	  | `4. Processes` | Identify the internal processes, sources, and destinations associated with the services. | PID, Processed Data, Tasks, Source, Destination |
	  | `5. Privileges` | Identification of the internal permissions and privileges to the accessible services. | Groups, Users, Permissions, Restrictions, Environment |
	  | `6. OS Setup` | Identification of the internal components and systems setup. | OS Type, Patch Level, Network config, OS Environment, Configuration files, sensitive private files |
	- ##### Infrastructure Based Enumeration
		- Domain Information
		  collapsed:: true
			- A good way to check for domains for a given target is https://crt.sh ![image.png](../assets/image_1693607832076_0.png)
			- Shodan can also be used but you have to use the paid versions
				- ```
				  iblis@htb[/htb]**$** for i in $(cat subdomainlist);do host $i | grep "has address" | grep inlanefreight.com | cut -d" " -f4 >> ip-addresses.txt;done
				  iblis@htb[/htb]**$** for i in $(cat ip-addresses.txt);do shodan host $i;done
				  - 10.129.24.93
				  City:                    Berlin
				  Country:                 Germany
				  Organization:            InlaneFreight
				  Updated:                 2021-09-01T09:02:11.370085
				  Number of open ports:    2
				  - Ports:
				     80/tcp nginx 
				    443/tcp nginx 
				  
				  10.129.27.33
				  City:                    Berlin
				  Country:                 Germany
				  Organization:            InlaneFreight
				  Updated:                 2021-08-30T22:25:31.572717
				  Number of open ports:    3
				  Ports:
				     22/tcp OpenSSH (7.6p1 Ubuntu-4ubuntu0.3)
				     80/tcp nginx 
				    443/tcp nginx 
				        |-- SSL Versions: -SSLv2, -SSLv3, -TLSv1, -TLSv1.1, -TLSv1.3, TLSv1.2
				        |-- Diffie-Hellman Parameters:
				                Bits:          2048
				                Generator:     2
				  		
				  10.129.27.22
				  City:                    Berlin
				  Country:                 Germany
				  Organization:            InlaneFreight
				  Updated:                 2021-09-01T15:39:55.446281
				  Number of open ports:    8
				  Ports:
				     25/tcp  
				        |-- SSL Versions: -SSLv2, -SSLv3, -TLSv1, -TLSv1.1, TLSv1.2, TLSv1.3
				     53/tcp  
				     53/udp  
				     80/tcp Apache httpd 
				     81/tcp Apache httpd 
				    110/tcp  
				        |-- SSL Versions: -SSLv2, -SSLv3, -TLSv1, -TLSv1.1, TLSv1.2
				    111/tcp  
				    443/tcp Apache httpd 
				        |-- SSL Versions: -SSLv2, -SSLv3, -TLSv1, -TLSv1.1, TLSv1.2, TLSv1.3
				        |-- Diffie-Hellman Parameters:
				                Bits:          2048
				                Generator:     2
				                Fingerprint:   RFC3526/Oakley Group 14
				    444/tcp  
				  
				  10.129.27.33
				  City:                    Berlin
				  Country:                 Germany
				  Organization:            InlaneFreight
				  Updated:                 2021-08-30T22:25:31.572717
				  Number of open ports:    3
				  Ports:
				     22/tcp OpenSSH (7.6p1 Ubuntu-4ubuntu0.3)
				     80/tcp nginx 
				    443/tcp nginx 
				        |-- SSL Versions: -SSLv2, -SSLv3, -TLSv1, -TLSv1.1, -TLSv1.3, TLSv1.2
				        |-- Diffie-Hellman Parameters:
				                Bits:          2048
				                Generator:     2
				  ```
			- #dig is also another great tool for finding all DNS records
			- By searching for the Domain information we can start to enumerate the client with more information
				- ```
				  ...SNIP... TXT     "MS=ms92346782372"
				  ...SNIP... TXT     "atlassian-domain-verification=IJdXMt1rKCy68JFszSdCKVpwPN"
				  ...SNIP... TXT     "google-site-verification=O7zV5-xFh_jn7JQ31"
				  ...SNIP... TXT     "google-site-verification=bow47-er9LdgoUeah"
				  ...SNIP... TXT     "google-site-verification=gZsCG-BINLopf4hr2"
				  ...SNIP... TXT     "logmein-verification-code=87123gff5a479e-61d4325gddkbvc1-b2bnfghfsed1-3c789427sdjirew63fc"
				  ...SNIP... TXT     "v=spf1 include:mailgun.org include:_spf.google.com include:spf.protection.outlook.com include:_spf.atlassian.net ip4:10.129.24.8 ip4:10.129.27.2 ip4:10.72.82.106 ~all"
				  ```
				- from these TXT records we know the target uses Atlassian, mailgun, google gmail, Outlook and Logmein
		- Cloud Resources
			- Noways almost all company's rely on cloud services some big players in the field are AWS, GCP, Azure
			- Using shodan you can find these targets
			- ```
			  iblis@htb[/htb]**$** for i in $(cat subdomainlist);do host $i | grep "has address" | grep inlanefreight.com | cut -d" " -f1,4;done
			  - blog.inlanefreight.com 10.129.24.93
			  inlanefreight.com 10.129.27.33
			  matomo.inlanefreight.com 10.129.127.22
			  www.inlanefreight.com 10.129.127.33
			  s3-website-us-west-2.amazonaws.com 10.129.95.250
			  ```
			- Third-party providers such as [domain.glass](https://domain.glass/) can also tell us a lot about the company's infrastructure. As a positive side effect, we can also see that Cloudflare's security assessment status has been classified as "Safe". This means we have already found a security measure that can be noted for the second layer (gateway).
			- Domain.Glass Results
			- ![](https://academy.hackthebox.com/storage/modules/112/cloud1.png)
			- nother very useful provider is [GrayHatWarfare](https://buckets.grayhatwarfare.com/). We can do many different searches, discover AWS, Azure, and GCP cloud storage, and even sort and filter by file format. Therefore, once we have found them through Google, we can also search for them on GrayHatWarefare and passively discover what files are stored on the given cloud storage.
			- #### GrayHatWarfare Results
			- ![](https://academy.hackthebox.com/storage/modules/112/cloud2.png)
			- Many companies also use abbreviations of the company name, which are then used accordingly within the IT infrastructure. Such terms are also part of an excellent approach to discovering new cloud storage from the company. We can also search for files simultaneously to see the files that can be accessed at the same time.
			- #### Private and Public SSH Keys Leaked
			- ![](https://academy.hackthebox.com/storage/modules/112/ghw1.png)
			- Sometimes when employees are overworked or under high pressure, mistakes can be fatal for the entire company. These errors can even lead to SSH private keys being leaked, which anyone can download and log onto one or even more machines in the company without using a password.
			- #### SSH Private Key
			- ![](https://academy.hackthebox.com/storage/modules/112/ghw2.png)
			-
	- ##### Host Based Enumeration
		- FTP
		  collapsed:: true
			- How does FTP work
			  collapsed:: true
				- FTP (File Transfer Protocol) servers connect to users through a client-server model. When a user initiates a connection to an FTP server, a series of steps take place to establish and maintain the connection.
				  
				  First, the FTP client (user) sends a connection request to the FTP server. The server listens for incoming connection requests on a designated port, usually port 21. The client's request includes the server's IP address or domain name.
				  
				  Once the server receives the request, it verifies the credentials provided by the client, such as a username and password. If the credentials are valid, the server responds with an acknowledgement, indicating that the client is allowed to connect.
				  
				  Upon successful authentication, the client and server start a control channel connection. The control channel is responsible for managing the commands and responses between the client and server throughout the FTP session.
				  
				  Now, the client can issue various commands (e.g., listing directories, uploading, or downloading files) using the control channel. These commands are sent to the server, which interprets and executes them accordingly.
				  
				  When it comes to transferring files, the FTP server opens a separate data channel to transmit the data. There are two modes for data transfer: active and passive. In active mode, the server initiates the connection to the client. In passive mode, the client establishes the connection to the server. Data channels use different ports (typically port 20) than the control channel.
				  
				  Once the data transfer is complete, the data channel is closed, while the control channel remains open for further communication. The client can send additional commands or choose to disconnect from the server, terminating the control channel connection.
			- Default Configurations
				- | **Commands**         | **Description** |
				  | ---- | ---- | ---- |
				  | `connect`  | Sets the remote host, and optionally the port, for file transfers. |
				  | `get` | Transfers a file or set of files from the remote host to the local host. |
				  | `put` | Transfers a file or set of files from the local host onto the remote host. |
				  | `quit` | Exits tftp. |
				  | `status` | Shows the current status of tftp, including the current transfer mode (ascii or binary), connection status, time-out value, and so on. |
				  | `verbose` | Turns verbose mode, which displays additional information during file transfer, on or off. |
				- #### vsFTPd Config File
				- ```
				  iblis@htb[/htb]**$** cat /etc/vsftpd.conf | grep -v "#"
				  ```
				  | **Setting** | **Description** |
				  | ---- | ---- | ---- |
				  | `listen=NO` | Run from inetd or as a standalone daemon? |
				  | `listen_ipv6=YES` | Listen on IPv6 ? |
				  | `anonymous_enable=NO` | Enable Anonymous access? |
				  | `local_enable=YES` | Allow local users to login? |
				  | `dirmessage_enable=YES` | Display active directory messages when users go into certain directories? |
				  | `use_localtime=YES` | Use local time? |
				  | `xferlog_enable=YES` | Activate logging of uploads/downloads? |
				  | `connect_from_port_20=YES` | Connect from port 20? |
				  | `secure_chroot_dir=/var/run/vsftpd/empty` | Name of an empty directory |
				  | `pam_service_name=vsftpd` | This string is the name of the PAM service vsftpd will use. |
				  | `rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem` | The last three options specify the location of the RSA certificate to use for SSL encrypted connections. |
				  | `rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key` |  |
				  | `ssl_enable=NO` |  |
				- In addition, there is a file called `/etc/ftpusers` that we also need to pay attention to, as this file is used to deny certain users access to the FTP service. In the following example, the users `guest`, `john`, and `kevin` are not permitted to log in to the FTP service, even if they exist on the Linux system.
				- #### FTPUSERS
				- ```
				  iblis@htb[/htb]**$** cat /etc/ftpusers
				  - guest
				  john
				  kevin
				  ```
				- ---
				- ## Dangerous Settings
				- There are many different security-related settings we can make on each FTP server. These can have various purposes, such as testing connections through the firewalls, testing routes, and authentication mechanisms. One of these authentication mechanisms is the `anonymous` user. This is often used to allow everyone on the internal network to share files and data without accessing each other's computers. With vsFTPd, the [optional settings](http://vsftpd.beasts.org/vsftpd_conf.html) that can be added to the configuration file for the anonymous login look like this:
				  | **Setting** | **Description** |
				  | ---- | ---- | ---- |
				  | `anonymous_enable=YES` | Allowing anonymous login? |
				  | `anon_upload_enable=YES` | Allowing anonymous to upload files? |
				  | `anon_mkdir_write_enable=YES` | Allowing anonymous to create new directories? |
				  | `no_anon_password=YES` | Do not ask anonymous for password? |
				  | `anon_root=/home/username/ftp` | Directory for anonymous. |
				  | `write_enable=YES` | Allow the usage of FTP commands: STOR, DELE, RNFR, RNTO, MKD, RMD, APPE, and SITE? |
				- With the standard FTP client (`ftp`), we can access the FTP server accordingly and log in with the anonymous user if the settings shown above have been used. The use of the anonymous account can occur in internal environments and infrastructures where the participants are all known. Access to this type of service can be set temporarily or with the setting to accelerate the exchange of files.
				- As soon as we connect to the vsFTPd server, the `response code 220` is displayed with the banner of the FTP server. Often this banner contains the description of the `service` and even the `version` of it. It also tells us what type of system the FTP server is. One of the most common configurations of FTP servers is to allow `anonymous` access, which does not require legitimate credentials but provides access to some files. Even if we cannot download them, sometimes just listing the contents is enough to generate further ideas and note down information that will help us in another approach.
				- #### Anonymous Login
				- Anonymous Login
				- ```
				  iblis@htb[/htb]**$** ftp 10.129.14.136
				  - Connected to 10.129.14.136.
				  220 "Welcome to the HTB Academy vsFTP service."
				  Name (10.129.14.136:cry0l1t3): anonymous
				  - 230 Login successful.
				  Remote system type is UNIX.
				  Using binary mode to transfer files.
				  - ftp> ls
				  200 PORT command successful. Consider using PASV.
				  150 Here comes the directory listing.
				  -rw-rw-r--    1 1002     1002      8138592 Sep 14 16:54 Calender.pptx
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Clients
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Documents
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Employees
				  -rw-rw-r--    1 1002     1002           41 Sep 14 16:45 Important Notes.txt
				  226 Directory send OK.
				  ```
				- However, to get the first overview of the server's settings, we can use the following command:
				- #### vsFTPd Status
				- vsFTPd Status
				- ```
				  ftp> status
				  - Connected to 10.129.14.136.
				  No proxy connection.
				  Connecting using address family: any.
				  Mode: stream; Type: binary; Form: non-print; Structure: file
				  Verbose: on; Bell: off; Prompting: on; Globbing: on
				  Store unique: off; Receive unique: off
				  Case: off; CR stripping: on
				  Quote control characters: on
				  Ntrans: off
				  Nmap: off
				  Hash mark printing: off; Use of PORT cmds: on
				  Tick counter printing: off
				  ```
				- Some commands should be used occasionally, as these will make the server show us more information that we can use for our purposes. These commands include `debug` and `trace`.
				- #### vsFTPd Detailed Output
				- vsFTPd Detailed Output
				- ```
				  ftp> debug
				  - Debugging on (debug=1).
				  - ftp> trace
				  - Packet tracing on.
				  - ftp> ls
				  ---> PORT 10,10,14,4,188,195
				  200 PORT command successful. Consider using PASV.
				  ---> LIST
				  150 Here comes the directory listing.
				  -rw-rw-r--    1 1002     1002      8138592 Sep 14 16:54 Calender.pptx
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 17:03 Clients
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Documents
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Employees
				  -rw-rw-r--    1 1002     1002           41 Sep 14 16:45 Important Notes.txt
				  226 Directory send OK.
				  ```
				  | **Setting** | **Description** |
				  | ---- | ---- | ---- |
				  | `dirmessage_enable=YES` | Show a message when they first enter a new directory? |
				  | `chown_uploads=YES` | Change ownership of anonymously uploaded files? |
				  | `chown_username=username` | User who is given ownership of anonymously uploaded files. |
				  | `local_enable=YES` | Enable local users to login? |
				  | `chroot_local_user=YES` | Place local users into their home directory? |
				  | `chroot_list_enable=YES` | Use a list of local users that will be placed in their home directory? |
				  | **Setting** | **Description** |
				  | ---- | ---- | ---- |
				  | `hide_ids=YES` | All user and group information in directory listings will be displayed as "ftp". |
				  | `ls_recurse_enable=YES` | Allows the use of recurse listings. |
				- In the following example, we can see that if the `hide_ids=YES` setting is present, the UID and GUID representation of the service will be overwritten, making it more difficult for us to identify with which rights these files are written and uploaded.
				- #### Hiding IDs - YES
				  Hiding IDs - YES
				- ```
				  ftp> ls
				  ---> TYPE A
				  200 Switching to ASCII mode.
				  ftp: setsockopt (ignored): Permission denied
				  ---> PORT 10,10,14,4,223,101
				  200 PORT command successful. Consider using PASV.
				  ---> LIST
				  150 Here comes the directory listing.
				  -rw-rw-r--    1 ftp     ftp      8138592 Sep 14 16:54 Calender.pptx
				  drwxrwxr-x    2 ftp     ftp         4096 Sep 14 17:03 Clients
				  drwxrwxr-x    2 ftp     ftp         4096 Sep 14 16:50 Documents
				  drwxrwxr-x    2 ftp     ftp         4096 Sep 14 16:50 Employees
				  -rw-rw-r--    1 ftp     ftp           41 Sep 14 16:45 Important Notes.txt
				  -rw-------    1 ftp     ftp            0 Sep 15 14:57 testupload.txt
				  226 Directory send OK.
				  ```
				- This setting is a security feature to prevent local usernames from being revealed. With the usernames, we could attack the services like FTP and SSH and many others with a brute-force attack in theory. However, in reality, [fail2ban](https://en.wikipedia.org/wiki/Fail2ban) solutions are now a standard implementation of any infrastructure that logs the IP address and blocks all access to the infrastructure after a certain number of failed login attempts.
				- Another helpful setting we can use for our purposes is the `ls_recurse_enable=YES`. This is often set on the vsFTPd server to have a better overview of the FTP directory structure, as it allows us to see all the visible content at once.
				- #### Recursive Listing
				- Recursive Listing
				- ```
				  ftp> ls -R
				  ---> PORT 10,10,14,4,222,149
				  200 PORT command successful. Consider using PASV.
				  ---> LIST -R
				  150 Here comes the directory listing.
				  .:
				  -rw-rw-r--    1 ftp      ftp      8138592 Sep 14 16:54 Calender.pptx
				  drwxrwxr-x    2 ftp      ftp         4096 Sep 14 17:03 Clients
				  drwxrwxr-x    2 ftp      ftp         4096 Sep 14 16:50 Documents
				  drwxrwxr-x    2 ftp      ftp         4096 Sep 14 16:50 Employees
				  -rw-rw-r--    1 ftp      ftp           41 Sep 14 16:45 Important Notes.txt
				  -rw-------    1 ftp      ftp            0 Sep 15 14:57 testupload.txt
				  ./Clients:
				  drwx------    2 ftp      ftp          4096 Sep 16 18:04 HackTheBox
				  drwxrwxrwx    2 ftp      ftp          4096 Sep 16 18:00 Inlanefreight
				  ./Clients/HackTheBox:
				  -rw-r--r--    1 ftp      ftp         34872 Sep 16 18:04 appointments.xlsx
				  -rw-r--r--    1 ftp      ftp        498123 Sep 16 18:04 contract.docx
				  -rw-r--r--    1 ftp      ftp        478237 Sep 16 18:04 contract.pdf
				  -rw-r--r--    1 ftp      ftp           348 Sep 16 18:04 meetings.txt
				  ./Clients/Inlanefreight:
				  -rw-r--r--    1 ftp      ftp         14211 Sep 16 18:00 appointments.xlsx
				  -rw-r--r--    1 ftp      ftp         37882 Sep 16 17:58 contract.docx
				  -rw-r--r--    1 ftp      ftp            89 Sep 16 17:58 meetings.txt
				  -rw-r--r--    1 ftp      ftp        483293 Sep 16 17:59 proposal.pptx
				  ./Documents:
				  -rw-r--r--    1 ftp      ftp         23211 Sep 16 18:05 appointments-template.xlsx
				  -rw-r--r--    1 ftp      ftp         32521 Sep 16 18:05 contract-template.docx
				  -rw-r--r--    1 ftp      ftp        453312 Sep 16 18:05 contract-template.pdf
				  - ./Employees:
				  226 Directory send OK.
				  ```
				- `Downloading` files from such an FTP server is one of the main features, as well as `uploading` files created by us. This allows us, for example, to use LFI vulnerabilities to make the host execute system commands. Apart from the files, we can view, download and inspect. Attacks are also possible with the FTP logs, leading to `Remote Command Execution` (`RCE`). This applies to the FTP services and all those we can detect during our enumeration phase.
				- Download a File
				- ```
				  ftp> ls
				  - 200 PORT command successful. Consider using PASV.
				  150 Here comes the directory listing.
				  -rwxrwxrwx    1 ftp      ftp             0 Sep 16 17:24 Calendar.pptx
				  drwxrwxrwx    4 ftp      ftp          4096 Sep 16 17:57 Clients
				  drwxrwxrwx    2 ftp      ftp          4096 Sep 16 18:05 Documents
				  drwxrwxrwx    2 ftp      ftp          4096 Sep 16 17:24 Employees
				  -rwxrwxrwx    1 ftp      ftp            41 Sep 18 15:58 Important Notes.txt
				  226 Directory send OK.
				  - ftp> get Important\ Notes.txt
				  - local: Important Notes.txt remote: Important Notes.txt
				  200 PORT command successful. Consider using PASV.
				  150 Opening BINARY mode data connection for Important Notes.txt (41 bytes).
				  226 Transfer complete.
				  41 bytes received in 0.00 secs (606.6525 kB/s)
				  - ftp> exit
				  - 221 Goodbye.
				  ```
				- Download a File
				- ```
				  iblis@htb[/htb]**$** ls | grep Notes.txt
				  - 'Important Notes.txt'
				  ```
				- We also can download all the files and folders we have access to at once. This is especially useful if the FTP server has many different files in a larger folder structure. However, this can cause alarms because no one from the company usually wants to download all files and content all at once.
				- #### Download All Available Files
				- ```
				  iblis@htb[/htb]**$** wget -m --no-passive ftp://anonymous:anonymous@10.129.14.136
				  --2021-09-19 14:45:58--  ftp://anonymous:*password*@10.129.14.136/                                         
				           => ‘10.129.14.136/.listing’                                                                     
				  Connecting to 10.129.14.136:21... connected.                                                               
				  Logging in as anonymous ... Logged in!
				  ==> SYST ... done.    ==> PWD ... done.
				  ==> TYPE I ... done.  ==> CWD not needed.
				  ==> PORT ... done.    ==> LIST ... done.                                                                 
				  12.12.1.136/.listing           [ <=>                                  ]     466  --.-KB/s    in 0s       
				                                                                                                         
				  2021-09-19 14:45:58 (65,8 MB/s) - ‘10.129.14.136/.listing’ saved [466]                                     
				  --2021-09-19 14:45:58--  ftp://anonymous:*password*@10.129.14.136/Calendar.pptx   
				           => ‘10.129.14.136/Calendar.pptx’                                       
				  ==> CWD not required.                                                           
				  ==> SIZE Calendar.pptx ... done.                                                                                                                            
				  ==> PORT ... done.    ==> RETR Calendar.pptx ... done.
				  - ...SNIP...
				  2021-09-19 14:45:58 (48,3 MB/s) - ‘10.129.14.136/Employees/.listing’ saved [119]
				  FINISHED --2021-09-19 14:45:58--
				  Total wall clock time: 0,03s
				  Downloaded: 15 files, 1,7K in 0,001s (3,02 MB/s)
				  ```
				- Once we have downloaded all the files, `wget` will create a directory with the name of the IP address of our target. All downloaded files are stored there, which we can then inspect locally.
				- Download All Available Files
				- ```
				  iblis@htb[/htb]**$** tree .
				  - .
				  └── 10.129.14.136
				    ├── Calendar.pptx
				    ├── Clients
				    │   └── Inlanefreight
				    │       ├── appointments.xlsx
				    │       ├── contract.docx
				    │       ├── meetings.txt
				    │       └── proposal.pptx
				    ├── Documents
				    │   ├── appointments-template.xlsx
				    │   ├── contract-template.docx
				    │   └── contract-template.pdf
				    ├── Employees
				    └── Important Notes.txt
				  - 5 directories, 9 files
				  ```
				- Next, we can check if we have the permissions to upload files to the FTP server. Especially with web servers, it is common that files are synchronized, and the developers have quick access to the files. FTP is often used for this purpose, and most of the time, configuration errors are found on servers that the administrators think are not discoverable. The attitude that internal network components cannot be accessed from the outside means that the hardening of internal systems is often neglected and leads to misconfigurations.
				- The ability to upload files to the FTP server connected to a web server increases the likelihood of gaining direct access to the webserver and even a reverse shell that allows us to execute internal system commands and perhaps even escalate our privileges.
				- #### Upload a File
				- ```
				  iblis@htb[/htb]**$** touch testupload.txt
				  ```
				- With the `PUT` command, we can upload files in the current folder to the FTP server.
				- Upload a File
				- ```
				  ftp> put testupload.txt
				  - local: testupload.txt remote: testupload.txt
				  ---> PORT 10,10,14,4,184,33
				  200 PORT command successful. Consider using PASV.
				  ---> STOR testupload.txt
				  150 Ok to send data.
				  226 Transfer complete.
				  - ftp> ls
				  ---> TYPE A
				  200 Switching to ASCII mode.
				  ---> PORT 10,10,14,4,223,101
				  200 PORT command successful. Consider using PASV.
				  ---> LIST
				  150 Here comes the directory listing.
				  -rw-rw-r--    1 1002     1002      8138592 Sep 14 16:54 Calender.pptx
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 17:03 Clients
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Documents
				  drwxrwxr-x    2 1002     1002         4096 Sep 14 16:50 Employees
				  -rw-rw-r--    1 1002     1002           41 Sep 14 16:45 Important Notes.txt
				  -rw-------    1 1002     133             0 Sep 15 14:57 testupload.txt
				  226 Directory send OK.
				  ```
				- Foot Printing using Nmap for FTP
				- #### Nmap FTP Scripts
				- ```
				  iblis@htb[/htb]**$** sudo nmap --script-updatedb
				  - Starting Nmap 7.80 ( https://nmap.org ) at 2021-09-19 13:49 CEST
				  NSE: Updating rule database.
				  NSE: Script Database updated successfully.
				  Nmap done: 0 IP addresses (0 hosts up) scanned in 0.28 seconds
				  ```
				- All the NSE scripts are located on the Pwnbox in `/usr/share/nmap/scripts/`, but on our systems, we can find them using a simple command on our system.
				- Nmap FTP Scripts
				- ```
				  iblis@htb[/htb]**$** find / -type f -name ftp* **2**>/dev/null | grep scripts
				  - /usr/share/nmap/scripts/ftp-syst.nse
				  /usr/share/nmap/scripts/ftp-vsftpd-backdoor.nse
				  /usr/share/nmap/scripts/ftp-vuln-cve2010-4221.nse
				  /usr/share/nmap/scripts/ftp-proftpd-backdoor.nse
				  /usr/share/nmap/scripts/ftp-bounce.nse
				  /usr/share/nmap/scripts/ftp-libopie.nse
				  /usr/share/nmap/scripts/ftp-anon.nse
				  /usr/share/nmap/scripts/ftp-brute.nse
				  ```
				- As we already know, the FTP server usually runs on the standard TCP port 21, which we can scan using Nmap. We also use the version scan (`-sV`), aggressive scan (`-A`), and the default script scan (`-sC`) against our target `10.129.14.136`.
				- #### Nmap
				- ```
				  iblis@htb[/htb]**$** sudo nmap -sV -p21 -sC -A 10.129.14.136
				  - Starting Nmap 7.80 ( https://nmap.org ) at 2021-09-16 18:12 CEST
				  Nmap scan report for 10.129.14.136
				  Host is up (0.00013s latency).
				  PORT   STATE SERVICE VERSION
				  21/tcp open  ftp     vsftpd 2.0.8 or later
				  | ftp-anon: Anonymous FTP login allowed (FTP code 230)
				  | -rwxrwxrwx    1 ftp      ftp       8138592 Sep 16 17:24 Calendar.pptx [NSE: writeable]
				  | drwxrwxrwx    4 ftp      ftp          4096 Sep 16 17:57 Clients [NSE: writeable]
				  | drwxrwxrwx    2 ftp      ftp          4096 Sep 16 18:05 Documents [NSE: writeable]
				  | drwxrwxrwx    2 ftp      ftp          4096 Sep 16 17:24 Employees [NSE: writeable]
				  | -rwxrwxrwx    1 ftp      ftp            41 Sep 16 17:24 Important Notes.txt [NSE: writeable]
				  |_-rwxrwxrwx    1 ftp      ftp             0 Sep 15 14:57 testupload.txt [NSE: writeable]
				  | ftp-syst: 
				  |   STAT: 
				  | FTP server status:
				  |      Connected to 10.10.14.4
				  |      Logged in as ftp
				  |      TYPE: ASCII
				  |      No session bandwidth limit
				  |      Session timeout in seconds is 300
				  |      Control connection is plain text
				  |      Data connections will be plain text
				  |      At session startup, client count was 2
				  |      vsFTPd 3.0.3 - secure, fast, stable
				  |_End of status
				  ```
				- The default script scan is based on the services' fingerprints, responses, and standard ports. Once Nmap has detected the service, it executes the marked scripts one after the other, providing different information. For example, the [ftp-anon](https://nmap.org/nsedoc/scripts/ftp-anon.html) NSE script checks whether the FTP server allows anonymous access. If so, the contents of the FTP root directory are rendered for the anonymous user.
				- The `ftp-syst`, for example, executes the `STAT` command, which displays information about the FTP server status. This includes configurations as well as the version of the FTP server. Nmap also provides the ability to trace the progress of NSE scripts at the network level if we use the `--script-trace` option in our scans. This lets us see what commands Nmap sends, what ports are used, and what responses we receive from the scanned server.
				- #### Nmap Script Trace
				- Nmap Script Trace
				- ```
				  iblis@htb[/htb]**$** sudo nmap -sV -p21 -sC -A 10.129.14.136 --script-trace
				  - Starting Nmap 7.80 ( https://nmap.org ) at 2021-09-19 13:54 CEST                                                                                                                                                   
				  NSOCK INFO [11.4640s] nsock_trace_handler_callback(): Callback: CONNECT SUCCESS for EID 8 [10.129.14.136:21]                                   
				  NSOCK INFO [11.4640s] nsock_trace_handler_callback(): Callback: CONNECT SUCCESS for EID 16 [10.129.14.136:21]             
				  NSOCK INFO [11.4640s] nsock_trace_handler_callback(): Callback: CONNECT SUCCESS for EID 24 [10.129.14.136:21]
				  NSOCK INFO [11.4640s] nsock_trace_handler_callback(): Callback: CONNECT SUCCESS for EID 32 [10.129.14.136:21]
				  NSOCK INFO [11.4640s] nsock_read(): Read request from IOD **#**1 [10.129.14.136:21] (timeout: 7000ms) EID 42
				  NSOCK INFO [11.4640s] nsock_read(): Read request from IOD **#**2 [10.129.14.136:21] (timeout: 9000ms) EID 50
				  NSOCK INFO [11.4640s] nsock_read(): Read request from IOD **#**3 [10.129.14.136:21] (timeout: 7000ms) EID 58
				  NSOCK INFO [11.4640s] nsock_read(): Read request from IOD **#**4 [10.129.14.136:21] (timeout: 11000ms) EID 66
				  NSE: TCP 10.10.14.4:54226 > 10.129.14.136:21 | CONNECT
				  NSE: TCP 10.10.14.4:54228 > 10.129.14.136:21 | CONNECT
				  NSE: TCP 10.10.14.4:54230 > 10.129.14.136:21 | CONNECT
				  NSE: TCP 10.10.14.4:54232 > 10.129.14.136:21 | CONNECT
				  NSOCK INFO [11.4660s] nsock_trace_handler_callback(): Callback: READ SUCCESS for EID 50 [10.129.14.136:21] (41 bytes): 220 Welcome to HTB-Academy FTP service...
				  NSOCK INFO [11.4660s] nsock_trace_handler_callback(): Callback: READ SUCCESS for EID 58 [10.129.14.136:21] (41 bytes): 220 Welcome to HTB-Academy FTP service...
				  NSE: TCP 10.10.14.4:54228 < 10.129.14.136:21 | 220 Welcome to HTB-Academy FTP service.
				  ```
				- The scan history shows that four different parallel scans are running against the service, with various timeouts. For the NSE scripts, we see that our local machine uses other output ports (`54226`, `54228`, `54230`, `54232`) and first initiates the connection with the `CONNECT` command. From the first response from the server, we can see that we are receiving the banner from the server to our second NSE script (`54228`) from the target FTP server. If necessary, we can, of course, use other applications such as `netcat` or `telnet` to interact with the FTP server.
				- #### Service Interaction
				- Service Interaction
				- ```
				  iblis@htb[/htb]**$** nc -nv 10.129.14.136 21
				  ```
				- Service Interaction
				- ```
				  iblis@htb[/htb]**$** telnet 10.129.14.136 21
				  ```
				- It looks slightly different if the FTP server runs with TLS/SSL encryption. Because then we need a client that can handle TLS/SSL. For this, we can use the client `openssl` and communicate with the FTP server. The good thing about using `openssl` is that we can see the SSL certificate, which can also be helpful.
				- Service Interaction
				- ```
				  iblis@htb[/htb]**$** openssl s_client -connect 10.129.14.136:21 -starttls ftp
				  - CONNECTED(00000003)                                                                                      
				  Can't use SSL_get_servername                        
				  depth=0 C = US, ST = California, L = Sacramento, O = Inlanefreight, OU = Dev, CN = master.inlanefreight.htb, emailAddress = admin@inlanefreight.htb
				  verify error:num=18:self signed certificate
				  verify return:1
				  depth=0 C = US, ST = California, L = Sacramento, O = Inlanefreight, OU = Dev, CN = master.inlanefreight.htb, emailAddress = admin@inlanefreight.htb
				  verify return:1
				  ---                                                 
				  Certificate chain
				  0 s:C = US, ST = California, L = Sacramento, O = Inlanefreight, OU = Dev, CN = master.inlanefreight.htb, emailAddress = admin@inlanefreight.htb
				  
				  i:C = US, ST = California, L = Sacramento, O = Inlanefreight, OU = Dev, CN = master.inlanefreight.htb, emailAddress = admin@inlanefreight.htb
				  ---
				  
				  Server certificate
				  - -----BEGIN CERTIFICATE-----
				  - MIIENTCCAx2gAwIBAgIUD+SlFZAWzX5yLs2q3ZcfdsRQqMYwDQYJKoZIhvcNAQEL
				  ...SNIP...
				  ```
			- lab
				- [2023-09-01_23-23-12.mkv](../assets/2023-09-01_23-23-12_1693629623679_0.mkv)
				-
				-
		- SMB
		  collapsed:: true
			- What is SMB
				- SMB, or Server Message Block, is a network protocol used for sharing files, printers, and other resources between computers in a network. It allows computers running different operating systems to communicate with each other. SMB operates on the application layer of the TCP/IP protocol suite and uses shared access tokens to authenticate and authorize users. It supports various features like file and printer sharing, directory browsing, remote administration, and inter-process communication. SMB uses NetBIOS or DNS for name resolution, and TCP/IP for data transmission. Its security features include encryption, authentication, and access control for protecting shared resources.
				- What a Default configuration looks like
					- ```
					  iblis@htb[/htb]**$** cat /etc/samba/smb.conf | grep -v "#\|\;"
					  - [global]
					   workgroup = DEV.INFREIGHT.HTB
					   server string = DEVSMB
					   log file = /var/log/samba/log.%m
					   max log size = 1000
					   logging = file
					   panic action = /usr/share/samba/panic-action %d
					  - server role = standalone server
					   obey pam restrictions = yes
					   unix password sync = yes
					  - passwd program = /usr/bin/passwd %u
					   passwd chat = *Enter\snew\s*\spassword:* %n\n *Retype\snew\s*\spassword:* %n\n *password\supdated\ssuccessfully* .
					  - pam password change = yes
					   map to guest = bad user
					   usershare allow guests = yes
					  - [printers]
					   comment = All Printers
					   browseable = no
					   path = /var/spool/samba
					   printable = yes
					   guest ok = no
					   read only = yes
					   create mask = 0700
					  - [print**$**]
					   comment = Printer Drivers
					   path = /var/lib/samba/printers
					   browseable = yes
					   read only = yes
					   guest ok = no
					  ```
					- | **Setting** | **Description** |
					  | ---- | ---- | ---- |
					  | `[sharename]` | The name of the network share. |
					  | `workgroup = WORKGROUP/DOMAIN` | Workgroup that will appear when clients query. |
					  | `path = /path/here/` | The directory to which user is to be given access. |
					  | `server string = STRING` | The string that will show up when a connection is initiated. |
					  | `unix password sync = yes` | Synchronize the UNIX password with the SMB password? |
					  | `usershare allow guests = yes` | Allow non-authenticated users to access defined shared? |
					  | `map to guest = bad user` | What to do when a user login request doesn't match a valid UNIX user? |
					  | `browseable = yes` | Should this share be shown in the list of available shares? |
					  | `guest ok = yes` | Allow connecting to the service without using a password? |
					  | `read only = yes` | Allow users to read files only? |
					  | `create mask = 0700` | What permissions need to be set for newly created files? |
					- ## Dangerous Settings
					- Some of the above settings already bring some sensitive options. However, suppose we question the settings listed below and ask ourselves what the employees could gain from them, as well as attackers. In that case, we will see what advantages and disadvantages the settings bring with them. Let us take the setting `browseable = yes` as an example. If we as administrators adopt this setting, the company's employees will have the comfort of being able to look at the individual folders with the contents. Many folders are eventually used for better organization and structure. If the employee can browse through the shares, the attacker will also be able to do so after successful access.
					  | **Setting** | **Description** |
					  | ---- | ---- | ---- |
					  | `browseable = yes` | Allow listing available shares in the current share? |
					  | `read only = no` | Forbid the creation and modification of files? |
					  | `writable = yes` | Allow users to create and modify files? |
					  | `guest ok = yes` | Allow connecting to the service without using a password? |
					  | `enable privileges = yes` | Honor privileges assigned to specific SID? |
					  | `create mask = 0777` | What permissions must be assigned to the newly created files? |
					  | `directory mask = 0777` | What permissions must be assigned to the newly created directories? |
					  | `logon script = script.sh` | What script needs to be executed on the user's login? |
					  | `magic script = script.sh` | Which script should be executed when the script gets closed? |
					  | `magic output = script.out` | Where the output of the magic script needs to be stored? |
					- #### SMBclient - Connecting to the Share
					- ```
					  iblis@htb[/htb]**$** smbclient -N -L //10.129.14.128
					  Sharename       Type      Comment
					        ---------       ----      -------
					        print**$**          Disk      Printer Drivers
					        home            Disk      INFREIGHT Samba
					        dev             Disk      DEVenv
					        notes           Disk      CheckIT
					        IPC**$**            IPC       IPC Service (DEVSM)
					  SMB1 disabled -- no workgroup available
					  ```
					- The [Remote Procedure Call](https://www.geeksforgeeks.org/remote-procedure-call-rpc-in-operating-system/) (`RPC`) is a concept and, therefore, also a central tool to realize operational and work-sharing structures in networks and client-server architectures. The communication process via RPC includes passing parameters and the return of a function value.
					- #### RPCclient
					- RPCclient
					- ```
					  iblis@htb[/htb]**$** rpcclient -U "" 10.129.14.128
					  - Enter WORKGROUP\'s password:
					  rpcclient **$**>
					  ```
					- The `rpcclient` offers us many different requests with which we can execute specific functions on the SMB server to get information. A complete list of all these functions can be found on the [man page](https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html) of the rpcclient.
					  | **Query** | **Description** |
					  | ---- | ---- | ---- |
					  | `srvinfo` | Server information. |
					  | `enumdomains` | Enumerate all domains that are deployed in the network. |
					  | `querydominfo` | Provides domain, server, and user information of deployed domains. |
					  | `netshareenumall` | Enumerates all available shares. |
					  | `netsharegetinfo <share>` | Provides information about a specific share. |
					  | `enumdomusers` | Enumerates all domain users. |
					  | `queryuser <RID>` | Provides information about a specific user. |
					- rpcclient Enumeration
					- ```
					  rpcclient **$**> srvinfo
					  - DEVSMB         Wk Sv PrQ Unx NT SNT DEVSM
					        platform_id     :       500
					        os version      :       6.1
					        server type     :       0x809a03
					  
					  
					  rpcclient **$**> enumdomains
					  - name:[DEVSMB] idx:[0x0]
					  name:[Builtin] idx:[0x1]
					  - rpcclient **$**> querydominfo
					  - Domain:         DEVOPS
					  Server:         DEVSMB
					  Comment:        DEVSM
					  Total Users:    2
					  Total Groups:   0
					  Total Aliases:  0
					  Sequence No:    1632361158
					  Force Logoff:   -1
					  Domain Server State:    0x1
					  Server Role:    ROLE_DOMAIN_PDC
					  Unknown 3:      0x1
					  - rpcclient **$**> netshareenumall
					  - netname: print$
					        remark: Printer Drivers
					        path:   C:\var\lib\samba\printers
					        password:
					  netname: home
					        remark: INFREIGHT Samba
					        path:   C:\home\
					        password:
					  netname: dev
					        remark: DEVenv
					        path:   C:\home\sambauser\dev\
					        password:
					  netname: notes
					        remark: CheckIT
					        path:   C:\mnt\notes\
					        password:
					  netname: IPC$
					        remark: IPC Service (DEVSM)
					        path:   C:\tmp
					        password:
					  
					  
					  rpcclient **$**> netsharegetinfo notes
					  netname: notes
					        remark: CheckIT
					        path:   C:\mnt\notes\
					        password:
					        type:   0x0
					        perms:  0
					        max_uses:       -1
					        num_uses:       1
					  revision: 1
					  type: 0x8004: SEC_DESC_DACL_PRESENT SEC_DESC_SELF_RELATIVE 
					  DACL
					        ACL     Num ACEs:       1       revision:       2
					        ---
					        ACE
					                type: ACCESS ALLOWED (0) flags: 0x00 
					                Specific bits: 0x1ff
					                Permissions: 0x101f01ff: Generic all access SYNCHRONIZE_ACCESS WRITE_OWNER_ACCESS WRITE_DAC_ACCESS READ_CONTROL_ACCESS DELETE_ACCESS 
					                SID: S-1-1-0
					  ```
					- #### Rpcclient - User Enumeration
					- ```
					  rpcclient **$**> enumdomusers
					  - user:[mrb3n] rid:[0x3e8]
					  user:[cry0l1t3] rid:[0x3e9]
					  - rpcclient **$**> queryuser 0x3e9
					  - User Name   :   cry0l1t3
					        Full Name   :   cry0l1t3
					        Home Drive  :   \\devsmb\cry0l1t3
					        Dir Drive   :
					        Profile Path:   \\devsmb\cry0l1t3\profile
					        Logon Script:
					        Description :
					        Workstations:
					        Comment     :
					        Remote Dial :
					        Logon Time               :      Do, 01 Jan 1970 01:00:00 CET
					        Logoff Time              :      Mi, 06 Feb 2036 16:06:39 CET
					        Kickoff Time             :      Mi, 06 Feb 2036 16:06:39 CET
					        Password last set Time   :      Mi, 22 Sep 2021 17:50:56 CEST
					        Password can change Time :      Mi, 22 Sep 2021 17:50:56 CEST
					        Password must change Time:      Do, 14 Sep 30828 04:48:05 CEST
					        unknown_2[0..31]...
					        user_rid :      0x3e9
					        group_rid:      0x201
					        acb_info :      0x00000014
					        fields_present: 0x00ffffff
					        logon_divs:     168
					        bad_password_count:     0x00000000
					        logon_count:    0x00000000
					        padding1[0..7]...
					        logon_hrs[0..21]...
					  - rpcclient **$**> queryuser 0x3e8
					  - User Name   :   mrb3n
					        Full Name   :
					        Home Drive  :   \\devsmb\mrb3n
					        Dir Drive   :
					        Profile Path:   \\devsmb\mrb3n\profile
					        Logon Script:
					        Description :
					        Workstations:
					        Comment     :
					        Remote Dial :
					        Logon Time               :      Do, 01 Jan 1970 01:00:00 CET
					        Logoff Time              :      Mi, 06 Feb 2036 16:06:39 CET
					        Kickoff Time             :      Mi, 06 Feb 2036 16:06:39 CET
					        Password last set Time   :      Mi, 22 Sep 2021 17:47:59 CEST
					        Password can change Time :      Mi, 22 Sep 2021 17:47:59 CEST
					        Password must change Time:      Do, 14 Sep 30828 04:48:05 CEST
					        unknown_2[0..31]...
					        user_rid :      0x3e8
					        group_rid:      0x201
					        acb_info :      0x00000010
					        fields_present: 0x00ffffff
					        logon_divs:     168
					        bad_password_count:     0x00000000
					        logon_count:    0x00000000
					        padding1[0..7]...
					        logon_hrs[0..21]...
					  ```
					- #### SMBmap
					- SMBmap
					- ```
					  iblis@htb[/htb]**$** smbmap -H 10.129.14.128
					  [+] Finding open SMB ports....
					  [+] User SMB session established on 10.129.14.128...
					  [+] IP: 10.129.14.128:445       Name: 10.129.14.128                                     
					        Disk                                                    Permissions     Comment
					        ----                                                    -----------     -------
					        print**$**                                                  NO ACCESS       Printer Drivers
					        home                                                    NO ACCESS       INFREIGHT Samba
					        dev                                                     NO ACCESS       DEVenv
					        notes                                                   NO ACCESS       CheckIT
					        IPC**$**                                                    NO ACCESS       IPC Service (DEVSM)
					  ```
					- lab
						- [2023-09-02_00-00-37.mkv](../assets/2023-09-02_00-00-37_1693633085627_0.mkv)
						-
		- NFS
		-