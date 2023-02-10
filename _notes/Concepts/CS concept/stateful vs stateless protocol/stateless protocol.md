1. What is a Stateless protocol?

	- A stateless protocol is a communication protocol in which the server ***does not store any information about the client between requests.

	- In a stateless protocol, the server treats each request as an independent transaction, and does not retain any knowledge of previous requests from the same client. 

	- ***This means that the server does not keep track of the client's session state, and does not have any memory of previous requests made by the same client.![[Pasted image 20230202030733.png]]

2. Example of a Stateless protocol
	- HTTP and DNS


In general, stateless protocols are considered to be simpler and more scalable than stateful protocols, as they do not require the server to store any information about the client between requests. However, stateful protocols can be useful in certain cases, such as when the server needs to maintain information about the client's session state in order to provide the appropriate response.