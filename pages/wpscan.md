- WPScan is a free and open-source tool written in Ruby that is used to scan WordPress websites for known vulnerabilities in both WordPress core and commonly used WordPress plugins and themes. WPScan is a command-line tool that uses the WPScan WordPress Vulnerability Database to scan for WordPress vulnerabilities, plugin vulnerabilities, and theme vulnerabilities. The WPScan database is updated regularly by security specialists, developers, and the community at large. WPScan is a black box scanner, which means it mimics a real attacker and does not rely on any sort of access to the WordPress dashboard or source code to conduct the tests. WPScan is used by penetration testers, #network and system administrators, and cybersecurity enthusiasts to find potential security threats in WordPress websites. Some of the features of WPScan include:
- Scanning for WordPress vulnerabilities, plugin vulnerabilities, and theme vulnerabilities
- Mimicking a real attacker
- Using the WPScan WordPress Vulnerability Database
- Regularly updated by security specialists, developers, and the community at large
- Black box scanner
- Command-line tool
  
  Here are some examples of how to use WPScan:
- Basic scan: ```wpscan --url [target]```
- Scan for vulnerable plugins: ```wpscan --url [target] --enumerate p```
- Scan for vulnerable themes: ```wpscan --url [target] --enumerate t```
- Scan for vulnerable users: ```wpscan --url [target] --enumerate u```
- Scan for vulnerable timthumbs: ```wpscan --url [target] --enumerate tt```
  
  WPScan is a useful tool for information gathering and reconnaissance during penetration testing and security auditing of WordPress websites.
  
  Citations:
  [1] https://www.golinuxcloud.com/wpscan-wordpress-vulnerability-scanner/
  [2] https://www.bugcrowd.com/glossary/wpscan-security-scanner/
  [3] https://geekflare.com/wordpress-vulnerability-scanner-wpscan/
  [4] https://blog.sucuri.net/2021/05/wpscan-how-to-scan-for-wordpress-vulnerabilities.html
  [5] https://www.wpwhitesecurity.com/wpscan-wordpress-security-scanner/
  [6] https://www.digitalocean.com/community/tutorials/how-to-use-wpscan-to-test-for-vulnerable-plugins-and-themes-in-wordpress