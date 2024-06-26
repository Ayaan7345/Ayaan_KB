- Cisco operating systems
  id:: 64a1ca37-e084-4cc7-8415-b57558bc2666
	- ![04-02+Cisco+Operating+Systems.pdf](../assets/04-02+Cisco+Operating+Systems_1688324837319_0.pdf)
- Connecting to Cisco Devices over the #network
  id:: 64a1cae6-67dd-45fc-8eb3-c5fa27835da2
	- ![04-03a+Connecting+to+a+Cisco+Device+over+the+#networking.pdf](../assets/04-03a+Connecting+to+a+Cisco+Device+over+the+#networking_1688324910777_0.pdf)
	- In the real world you can use Putty or a Linux terminal to connect to a router over the #network
	- To configure or manage a Cisco device you have to connect to the management ip address.
	- In enterprise #network secure login will typically be enforeced with a central #AAA system Authentication, Authorization and Accounting server
- Making the initial connection
  id:: 64a1cd66-165a-4f5e-b389-87de3a111bdf
	- ![04-03b+Initial+Connection+to+a+Cisco+Device.pdf](../assets/04-03b+Initial+Connection+to+a+Cisco+Device_1688326191247_0.pdf)
	- When you get a brand new cisco device you have to add a ip address to it this can be done through a Console cable
- Navigating Cisco IOS
  id:: 64a1d5be-4c0a-4c65-b0e7-a6631f30b9b5
	- ![04-04+Navigating+the+Cisco+IOS+Operating+System.pdf](../assets/04-04+Navigating+the+Cisco+IOS+Operating+System_1688327633122_0.pdf)
	- hostname> is user Exec Mode
	- Hostname# Privliged Exec Mode (`en`)
	- hostname(config)# Global Configuration mode (`config t`)
	- hostname(config-if)# interface Configuration mode (`int g0/0`)
	- `exit` go back on level
	- `end` goes back to privliged exec mode (`en`)
	- use a question mark when you need help
	- `show and debug` commands are in privileged exec mode
- Managing Cisco IOS
  id:: 64a1dcf7-64d7-4586-bc11-47b042655401
	- ![04-05+IOS+Configuration+Management.pdf](../assets/04-05+IOS+Configuration+Management_1688329479373_0.pdf)
	- Enter `copy running-config startup-config` to make the configuration
	  persistent.
	- Enter `wr erase or erase startup-config` and then ``reload`` to delete
	  the starting configuration and factory reset the device.
- **The IOS Operating System - Lab Exercises**
  id:: 64a1de9a-09e2-4f6f-9ee9-3e4a325998d1
	- [04 The IOS Operating System.pkt](../assets/04_The_IOS_Operating_System_1688330141639_0.pkt)
	- ![04 The IOS Operating System - Lab Exercises.pdf](../assets/04_The_IOS_Operating_System_-_Lab_Exercises_1688330151099_0.pdf)
	-
	-