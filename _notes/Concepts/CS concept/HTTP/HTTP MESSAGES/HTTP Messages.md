1. What are the HTTP Messages?
	- HTTP messages are how data is exchanged between a server and a client. 
	
 2. Types of Http messages
	 1. Requests:  sent by the client to trigger an action on the server
	 2. Responses: the answer from the server.

3. What it is composed?
	- textual information encoded in ASCII, and span over(to extend over or across) multiple lines.

4. HTTP requests, and responses, share similar structure and are composed of:

	1.  A _start-line_ describing the requests to be implemented, or its status of whether successful or a failure. This start-line is always a single line.'

	2.  An optional set of _HTTP headers_ specifying the request, or describing the body included in the message.

	3.  A blank line indicating all meta-information for the request has been sent.

	4.  An optional _body_ containing data associated with the request (like content of an HTML form), or the document associated with a response. The presence of the body and its size is specified by the start-line and HTTP headers.
Example: 
- ![[http messages.excalidraw]]

- ![[Pasted image 20230204072209.png]]