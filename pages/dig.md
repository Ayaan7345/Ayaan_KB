- Dig is a command-line tool used for querying the Domain Name System (DNS) to obtain information about domain names, IP addresses, and other DNS records. It is a #networking administration tool that is used for verifying and troubleshooting DNS problems and to perform DNS lookups. Dig command replaces older tools such as nslookup and the host. It is part of the BIND domain name server software suite and is available in major Linux distributions. Dig can operate based on command line option and flag arguments, or in batch mode by reading requests from an operating system file. When a specific name server is not specified in the command invocation, it uses the operating system's default resolver, usually configured in the file resolv.conf. Without any arguments, it queries the DNS root zone. Dig supports Internationalized domain name (IDN) queries. It can be used to query domain “A” record, remove comment lines, query domain “A” record with +short, query a specific DNS server, perform a reverse DNS lookup, query a specific DNS server and record type, query a specific DNS server and port number, query a specific DNS server and query type, query a specific DNS server and query class, perform a DNS lookup with a specific DNS server and EDNS0 options, and perform a DNS lookup with a specific DNS server and #tcp protocol.
- Citations:
  [1] https://www.geeksforgeeks.org/dig-command-in-linux-with-examples/
  [2] https://www.tecmint.com/dig-command-examples/
  [3] https://en.wikipedia.org/wiki/Dig_(command)
  [4] https://phoenixnap.com/kb/linux-dig-command-examples
  [5] https://toolbox.googleapps.com/apps/dig/
  [6] https://www.cloudns.net/blog/10-most-used-dig-commands/
- A #DNS zone transfer **port 53 zone transfer attack ** is a method of copying DNS-related databases across different DNS servers. It is a type of DNS transaction that allows two DNS servers to exchange their zones. This is needed for redundancy. DNS zone transfers using the AXFR protocol are the simplest mechanism to replicate DNS records across DNS servers[2]. Zone transfers can be initiated using the Dig command, which is a command-line tool used for querying the DNS. To initiate a zone transfer using Dig, you simply specify axfr (as the query type) and the domain name of the zone as arguments[3]. However, if DNS zone transfers are done using the AXFR protocol, there is no encryption and there is no authentication. Anyone can get the whole zone using the AXFR protocol. Malicious hackers may use the information contained in zones to conduct attacks[1][2].
- Citations:
  [1] https://allabouttesting.org/top-5-commands-to-test-dns-zone-transfer-in-2-minutes/
  [2] https://www.acunetix.com/blog/articles/dns-zone-transfers-axfr/
  [3] https://docstore.mik.ua/orelly/##networking_2ndEd/dns/ch12_09.htm
  [4] https://flylib.com/books/en/2.684.1/transferring_a_zone_using_dig.html
  [5] https://hackertarget.com/zone-transfer/
  [6] https://infinitelogins.com/2020/04/23/performing-dns-zone-transfer/
- Dig example output
	- ```
	  iblis@htb[/htb]**$** dig any inlanefreight.com
	  ; <<>> DiG 9.16.1-Ubuntu <<>> any inlanefreight.com
	  ;; global options: +cmd
	  ;; Got answer:
	  ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 52058
	  ;; flags: qr rd ra; QUERY: 1, ANSWER: 17, AUTHORITY: 0, ADDITIONAL: 1
	  - ;; OPT PSEUDOSECTION:
	  ; EDNS: version: 0, flags:; udp: 65494
	  ;; QUESTION SECTION:
	  ;inlanefreight.com.             IN      ANY
	  - ;; ANSWER SECTION:
	  inlanefreight.com.      300     IN      A       10.129.27.33
	  inlanefreight.com.      300     IN      A       10.129.95.250
	  inlanefreight.com.      3600    IN      MX      1 aspmx.l.google.com.
	  inlanefreight.com.      3600    IN      MX      10 aspmx2.googlemail.com.
	  inlanefreight.com.      3600    IN      MX      10 aspmx3.googlemail.com.
	  inlanefreight.com.      3600    IN      MX      5 alt1.aspmx.l.google.com.
	  inlanefreight.com.      3600    IN      MX      5 alt2.aspmx.l.google.com.
	  inlanefreight.com.      21600   IN      NS      ns.inwx.net.
	  inlanefreight.com.      21600   IN      NS      ns2.inwx.net.
	  inlanefreight.com.      21600   IN      NS      ns3.inwx.eu.
	  inlanefreight.com.      3600    IN      TXT     "MS=ms92346782372"
	  inlanefreight.com.      21600   IN      TXT     "atlassian-domain-verification=IJdXMt1rKCy68JFszSdCKVpwPN"
	  inlanefreight.com.      3600    IN      TXT     "google-site-verification=O7zV5-xFh_jn7JQ31"
	  inlanefreight.com.      300     IN      TXT     "google-site-verification=bow47-er9LdgoUeah"
	  inlanefreight.com.      3600    IN      TXT     "google-site-verification=gZsCG-BINLopf4hr2"
	  inlanefreight.com.      3600    IN      TXT     "logmein-verification-code=87123gff5a479e-61d4325gddkbvc1-b2bnfghfsed1-3c789427sdjirew63fc"
	  inlanefreight.com.      300     IN      TXT     "v=spf1 include:mailgun.org include:_spf.google.com include:spf.protection.outlook.com include:_spf.atlassian.net ip4:10.129.24.8 ip4:10.129.27.2 ip4:10.72.82.106 ~all"
	  inlanefreight.com.      21600   IN      SOA     ns.inwx.net. hostmaster.inwx.net. 2021072600 10800 3600 604800 3600
	  - ;; Query time: 332 msec
	  ;; SERVER: 127.0.0.53**#**53(127.0.0.53)
	  ;; WHEN: Mi Sep 01 18:27:22 CEST 2021
	  ;; MSG SIZE  rcvd: 940
	  ```
-