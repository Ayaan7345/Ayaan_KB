- #HTB
- Information given
- Information given
  id:: 64d92134-a624-4b5f-893c-ee5c8924676d
	- IP: 10.129.202.49
- Task 1
  collapsed:: true
- Task 1
	- Which #tcp port is open on the machine?
	- Used nmap scan to find out
	  ![image.png](../assets/image_1678059805494_0.png)
	- Found Redis on port 6379 
	  #+BEGIN_IMPORTANT
	  6379
	  #+END_IMPORTANT
	-
- Task 2
  collapsed:: true
- Task 2
	- Which service is running on the port that is open on the machine?
	- This information was found in the nmap scan 
	  #+BEGIN_IMPORTANT
	  REDIS
	  #+END_IMPORTANT
- Task 3
  collapsed:: true
- Task 3
	- What type of database is Redis? Choose from the following options: (i) In-memory Database, (ii) Traditional Database
	- in-memory database
- Task 4
  collapsed:: true
- Task 4
	- Which command-line utility is used to interact with the Redis server? Enter the program name you would enter into the terminal without any arguments.
	- redis-cli
- Task 5
  collapsed:: true
	- Which flag is used with the Redis command-line utility to specify the hostname?
	- -h
- Task 6
- Task 6
  collapsed:: true
	- Once connected to a Redis server, which command is used to obtain the information and statistics about the Redis server?
	- info
- Task 7
	- What is the version of the Redis server being used on the target machine?
	- 5.0.7
- Task 8
	- Which command is used to select the desired database in Redis?
	- select 0
- Task 9
	- How many keys are present inside the database with index 0?
	- 4
- Task 10
	- Which command is used to obtain all the keys in a database?
	- keys *