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
- how to factory reset cisco device what is the command
	- To factory reset a Cisco device, you can use the "write erase" command followed by the "reload" command. Here is the step-by-step process:
	  
	  1. Connect to the device using a terminal emulation program, such as PuTTY or SecureCRT.
	  2. Log in to the device using appropriate credentials (username and password) with administrative privileges.
	  3. Enter the privileged EXEC mode by typing "enable" and providing the enable password if required.
	  4. Enter global configuration mode by typing "configure terminal" or simply "config t".
	  5. Issue the "write erase" command to erase the configuration and return the device to its default factory settings. This command deletes the startup configuration file and removes any user-created files or configurations. Confirm the erase operation if prompted.
	  6. Save the changes and exit configuration mode by typing "exit" or pressing Ctrl+Z.
	  7. Issue the "reload" command to reboot the device. Confirm the reload if prompted.
	  8. Once the device restarts, it will be restored to its factory default settings.
	  
	  Please note that performing a factory reset erases all configurations, so ensure you have a backup of important configurations before proceeding.
-