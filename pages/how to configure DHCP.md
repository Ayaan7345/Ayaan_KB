- This is how you configure #DHCP on a Cisco Router
	- config t
	  #Setup DHCP Pool with the IP addrress you want and lease time 
	  ip dhcp pool POOL-NAME
	  network NETWORK-SUBNET-MASK
	  default-router DEFAULT-GATEWAY
	  dns-server DNS-SERVER-IP
	  lease DAYS HOURS MINUTES
	- ```bash
	  config t
	  #Setup DHCP Pool with the IP addrress you want and lease time 
	  ip dhcp pool POOL-NAME
	  network NETWORK-SUBNET-MASK
	  default-router DEFAULT-GATEWAY
	  dns-server DNS-SERVER-IP
	  lease DAYS HOURS MINUTES
	  # To enable DHCP go into the interface and then run these commands 
	  interface INTERFACE
	  ip address IP-ADDRESS SUBNET-MASK
	  ip helper-address DHCP-SERVER-IP
	  
	  ```
	  # To enable DHCP go into the interface and then run these commands 
	  interface INTERFACE
	  ip address IP-ADDRESS SUBNET-MASK
	  ip helper-address DHCP-SERVER-IP
-