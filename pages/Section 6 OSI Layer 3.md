- #OSI layer 3
  id:: 64a218d6-a3a6-4ddc-ab7c-dd13670d4382
	- is for routing packets and QOS quality of service
- #IP
	- IP is the best known layer 3 protocol IPv4
	- ip addressing is a logical addressing scheme
	- you can partition different parts of the #network with ip
-
- #IP headers
  id:: 64a201a6-19c1-4b75-af5d-e58c0c19124a
	- ![06-02+The+IP+Header.pdf](../assets/06-02+The+IP+Header_1688344539812_0.pdf)
	- ![image.png](../assets/image_1688345101496_0.png){:height 411, :width 744}
- 3 Main types of traffic
  id:: 64a21a12-2cf6-4bae-9c9a-97bb3afe1dad
	- ![06-03+Unicast,+Broadcast+and+Multicast+Traffic.pdf](../assets/06-03+Unicast,+Broadcast+and+Multicast+Traffic_1688345239895_0.pdf)
	- Unicast
		- goes to **one** host
		- ![image.png](../assets/image_1688345342272_0.png)
	- Multicast
		- is sent to one copy of a packet to multiple hosts on the #network
		- ![image.png](../assets/image_1688345578865_0.png)
	- Broadcast
		- is sent to the entire #network
		- routers do not forward broadcast traffic
		- ![image.png](../assets/image_1688345398094_0.png){:height 390, :width 681}
- How to count in bianary
  id:: 64a21b37-bad5-40df-aaa2-9aeacc5d373d
	- ![06-04+Converting+from+Decimal+to+Binary+-+updated.pdf](../assets/06-04+Converting+from+Decimal+to+Binary+-+updated_1688346035790_0.pdf)
	- |256|128|64|32|16|8|4|2|1|
		- |#Subnetting Range |  Subnet Mask | # of Subnets | # of Hosts/Subnet|
		  |--- | --- | --- | ---|
		  |256 | /8 | 2^24 | 2^7|
		  |128 | /9 | 2^23 | 2^8|
		  |64 | /10 | 2^22 | 2^9|
		  |32 | /11 | 2^21 | 2^10|
		  |16 | /12 | 2^20 | 2^11|
		  |8 | /13 | 2^19 | 2^12|
		  |4 | /14 | 2^18 | 2^13|
		  |2 | /15 | 2^17 | 2^14|
		  |1 | /16 | 2^16 | 2^15|
	- |0|1|1|1|1|0|1|1|0|0|
	- this is 236 in binary
	- 010111011 this is 179 in bianary
		- Binary
		  
		  | Binary | Description |
		  | --- | --- |
		  | 0 | Off/False |
		  | 1 | On/True |
- IPv4
  id:: 64a221c5-d1da-4479-b170-afc363c50f4a
	- ![06-05+IPv4+Addresses.pdf](../assets/06-05+IPv4+Addresses_1688349959311_0.pdf)
	- is written in 4 octetes or 00000000.00000000.00000000.00000000
	- 192.168.1.1 is 01100000.010101000.00000001.00000001
	- to get #IP information from a cisco device the command is `show ip interface brief` or `show interface`
	- #DHCP (dynamic host configuration protocol) this automatically assigns an ip address to a host
	- #static ip is a address that you want to keep this address and never change
	- ![06-06+Calculating+an+IPv4+Address+in+Binary.pdf](../assets/06-06+Calculating+an+IPv4+Address+in+Binary_1688350226198_0.pdf)
	- what is 192.168.10.15 in binary
		- 11000000.10101000.00001010.00001111
- flash cards
	- What is the main function of the #OSI Layer 3 (Network Layer)? #card
	  card-last-interval:: 4
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2024-03-22T04:40:55.968Z
	  card-last-reviewed:: 2024-03-18T04:40:55.969Z
	  card-last-score:: 3
		- Answer: The main function of the OSI Layer 3 is to provide routing and forwarding of data between different networks.
	- What are some protocols operating at the OSI Layer 3? #card
	  card-last-interval:: 4.14
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-03-22T07:41:19.124Z
	  card-last-reviewed:: 2024-03-18T04:41:19.125Z
	  card-last-score:: 5
		- Answer: Some protocols operating at Layer 3 include IP (Internet Protocol), ICMP (Internet Control Message Protocol), and routing protocols such as OSPF and BGP.
	- What addressing scheme is used at the OSI Layer 3? #card
	  card-last-interval:: 4.14
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-03-22T07:41:11.243Z
	  card-last-reviewed:: 2024-03-18T04:41:11.243Z
	  card-last-score:: 5
		- Answer: The OSI Layer 3 uses logical addressing, such as IP addresses, to identify devices on different networks.
	- What is the primary unit of data at the OSI Layer 3? #card
	  card-last-interval:: 4.14
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2024-03-22T07:40:38.617Z
	  card-last-reviewed:: 2024-03-18T04:40:38.618Z
	  card-last-score:: 5
		- Answer: The primary unit of data at Layer 3 is the packet, which contains both the data payload and header information for routing.
-