- Nikto is a free and open-source web server and web application scanner that can perform comprehensive tests against web servers for multiple security threats, including over 6700 potentially dangerous files/programs. Nikto can also perform checks for outdated web servers software, and version-specific problems. It was written and maintained by Sullo, CIRT, Inc. and was originally released in late 2001. Nikto is written in Perl and is available for Linux, Windows, and macOS. Nikto is a command-line tool, and it can be used to scan a single target, multiple targets, perform a ping-only scan, display port state reason, attempt to guess an unknown OS, service version detection, perform an RPC scan, scan specific ports or scan entire port ranges on a local or remote server, and exclude host/IP addresses for the scan. Nikto is a good tool for finding potential security threats in web applications. Some examples of Nikto commands are:
- Scan a single target: ```nikto [target]```
- Perform a ping-only scan: ```nikto -h [target]```
- Scan multiple targets: ```nikto -host [target1] -host [target2]```
- Display port state reason: ```nikto -Display [port-state-reason]```
- Attempt to guess an unknown OS: ```nikto -o [target]```
- Service version detection: ```nikto -Version [target]```
- Perform an RPC scan: ```nikto -rpc [target]```
- Scan specific ports or scan entire port ranges on a local or remote server: ```nikto -p [port] [target]``` or ```nikto -p [port-range] [target]```
  
  Nikto is a useful tool for #networking and system administrators, cybersecurity enthusiasts, and penetration testers to find potential security threats in web applications.
  
  Citations:
  [1] https://www.freecodecamp.org/news/an-introduction-to-web-server-scanning-with-nikto/
  [2] https://en.wikipedia.org/wiki/Nikto_(vulnerability_scanner)
  [3] https://www.comparitech.com/net-admin/nikto-review/
  [4] https://cirt.net/Nikto2
  [5] https://www.skillset.com/questions/which-of-the-following-tools-performs-comprehensive-tests-against-web-servers-including-dangerous-fi
  [6] https://hackertarget.com/nikto-website-scanner/