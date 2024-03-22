- Basic introduction
  id:: 64a0f550-af6f-4153-ac09-b18bb6cff08a
  collapsed:: true
	- ![03-02+A+(Very)+Basic+Introduction+to+##networking.pdf](../assets/03-02+A+(Very)+Basic+Introduction+to+##networking_1688270254072_0.pdf)
	- This is a basic #networking topology
	- When building a #networking there are some things to keep in mind
	- Topology
	  Speed
	  Cost
	  Security
	  Availability
	  Scalability
	  Reliability
- #OSI
  collapsed:: true
	- ![03-03+Open+Systems+Interconnection+OSI+Model+Overview.pdf](../assets/03-03+Open+Systems+Interconnection+OSI+Model+Overview_1688270343038_0.pdf)
	- OSI model the Open Systems internet
	- ![OSI Model Explained Summary:Definitions and Functions | CCNA QUESTIONS ...](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2F3.bp.blogspot.com%2F-5swPB9xcxfg%2FVIiAnVbe4NI%2FAAAAAAAANRs%2FlpGBkKiNeRE%2Fs1600%2F1-tutorial-osi-7-layer-model.gif&f=1&nofb=1&ipt=702cee4a78d3b4e9f5680a1f715389ce8dbb700c44e033f6c66b2471d6e40860&ipo=images)
	- Layer 1-4 is most of what the CCNA will cover
	- OSI model acronym’s Please Do Not Throw Sausage Pizza Away
- #tcpIP
  collapsed:: true
	- ![03-04+The+#tcpIP+Stack+(Transmission+Control+Protocol++Internet+Protocol).pdf](../assets/03-04+The+#tcpIP+Stack+(Transmission+Control+Protocol++Internet+Protocol)_1688271631996_0.pdf)
	- ![#tcp/IP Model - A Level Computer Science](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Flearnlearn.uk%2Falevelcs%2Fwp-content%2Fuploads%2Fsites%2F20%2F2020%2F06%2FOSI-to-#tcpIP-Model.png&f=1&nofb=1&ipt=5606510ead751b48fed2547dfc08deaf56fd9fe6eba3d8f2e2f37ce4e71881bd&ipo=images)
- The upper #OSI layer
  id:: 64a0fc64-31f3-4bb5-8306-c9eccc06e4e4
  collapsed:: true
	- ![03-05+The+Upper+OSI+Layers.pdf](../assets/03-05+The+Upper+OSI+Layers_1688271956636_0.pdf)
	- Layer 7 Application layer
		- This layer does not provide servies to any other osi layer
		- This layer helps with #networking services to make sure the data got there correctly
	- layer 6 Presentation layer
		- This layer translates the data for the end user to use
	- layer 5 session
		- This layer establishes manages and terminates the sessions between two hosts
		- this layer also manages the rate that data can pass
- The lower #OSI layers
  id:: 64a0fdd7-fcad-4691-9c10-e6685117e988
  collapsed:: true
	- ![03-06+The+Lower+OSI+Layers.pdf](../assets/03-06+The+Lower+OSI+Layers_1688272364899_0.pdf)
	  id:: 64b4c0a2-038e-4b9e-a555-031146b56a93
	- Layer 4 Transport
		- This is where #tcp or #UDP is used and the port number
			- This layer breaks down large files into smaller segments
	- layer 3 #networking
		- This is where the source and destination ip is solved
		- routers are on this layer
		- ip is logical addressing
	- Layer 2 Data-link
		- This layer deals with MAC Adresses
		- It defines how data is formatted for transmission and how to access the physical cable
	- Layer 1 pysical
		- This is the cable that is used to send data over
	-