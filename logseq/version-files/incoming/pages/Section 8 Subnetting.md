- Where to do #Subnetting practice /
- Where to do #Subnetting practice
- What are VLSM and can you give an example
	- VLSM stands for Variable Length Subnet Masking. It is a technique used in computer networking to divide a network into smaller subnets of different sizes, allowing for more efficient utilization of IP addresses.
	  
	  With VLSM, a network administrator can assign different subnet masks to different subnets within a larger network. This allows them to allocate IP addresses more precisely based on the needs of each subnet. It eliminates the requirement of using a fixed subnet mask, which can result in wasted IP addresses if all subnets are required to have the same number of hosts.
	  
	  Here's an example to illustrate VLSM: 
	  
	  Let's say we have a network with the IP address range 192.168.0.0/24. We need to divide this network into two smaller subnets, with one having 20 hosts and the other requiring 30 hosts.
	  
	  To accomplish this, we can use VLSM. We allocate the subnet with 20 hosts a subnet mask of /27 and assign it the network address 192.168.0.0/27. This gives us 30 available IP addresses (including network and broadcast addresses) for hosts.
	  
	  For the subnet requiring 30 hosts, we need a subnet mask that can accommodate at least 30 hosts. That would be a /27 subnet mask. We assign it the network address 192.168.0.32/27, which provides 62 available IP addresses for hosts.
	  
	  By utilizing VLSM, we have efficiently divided the original network into two subnets of different sizes, optimizing the IP address allocation based on the specific requirements of each subnet.
- Steps to do VLSM start with biggest network first and then continue going down the list.
- do not over thing on the CCNA do exactly what the exam ask for.
- Switch operation
-