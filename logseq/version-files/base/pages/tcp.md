- Give a Detailed explanation as to what #TCP is
	- #TCP, standing for Transmission Control Protocol, is a standardized method for transmitting or exchanging data over the internet or other networks. It's a protocol used along with the Internet Protocol (IP) to send data in the form of individual units known as packets between computers over the internet.
	  
	  #TCP is part of the suite of protocols known as TCP/IP that make the internet possible. It works in tandem with #IP, which defines how computers send packets of data to each other.
	  
	  #TCP's role is to ensure that all packets of data are sent and received in the correct order. It involves sending an acknowledgement receipt once the data is received. This allows #TCP to provide end-to-end reliability. 
	  
	  #TCP is a 'connection-oriented' protocol. This means that it requires a connection to be established before data can be sent. It involves a process known as a "three-way handshake", where the sending computer and the receiving computer exchange SYN (synchronize) and ACK (acknowledgement) packets before the actual data transmission begins. 
	  
	  #TCP also incorporates error checking and flow control mechanisms. Error checking is ensured by a checksum method, which verifies the integrity of the data. On the other hand, flow control prevents a sender from overwhelming a receiver with data it may not be able to process at high speed.
	  
	  Thus, #TCP ensures data is delivered over the #network accurately and in sequence which makes it a vital protocol for applications such as web browsing, emails, and #file transfers where data integrity is critical. However, this also makes #TCP slower and more resource-intensive compared to other protocols like #UDP (User Datagram Protocol) which doesn't involve checks and confirmations.
	-