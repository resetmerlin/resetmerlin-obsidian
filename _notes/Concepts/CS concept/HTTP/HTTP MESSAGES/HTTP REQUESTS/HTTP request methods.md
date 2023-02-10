1. What is HTTP request method? 

	- It is a part of an HTTP request that defines the type of operation that the request is asking the server to perform. 

	- In HTTP, a request method is often referred to as a "verb," and the target resource is referred to as a "noun."

2. Verb or Request method
	- Defines the type of action that the request is asking the server to perform, such as retrieving data (GET), submitting data (POST), updating data (PUT), or deleting data (DELETE).

3. Noun or target resources
	- It is the specific resource that the request is addressing, such as a specific file, database record, or API endpoint.

Example: 

- In the request `GET /api/users`, the verb is GET and the noun is `/api/users`. This request is asking the server to retrieve information about the users stored in the API, and the GET method is used because it is a request to retrieve data.

- In the request `POST /api/users`, the verb is POST and the noun is `/api/users`. This request is asking the server to submit data to create a new user in the API, and the POST method is used because it is a request to submit data.

4. Standard HTTP request method
	-   GET: Requests data from a specified resource. This is the most common HTTP method, used to retrieve information from the server.
    
	-   POST: Submits data to be processed by the specified resource. This method is often used to send information to the server, such as when submitting a form.
    
	-   PUT: Updates a current resource with new data. This method is used to replace an existing resource with a new one.
    
	-   DELETE: Deletes a specified resource. This method is used to delete a resource on the server.
    
	-   HEAD: Requests only the headers of a specified resource. This method is used to retrieve only the header information of a resource, without retrieving the resource itself.
    
	-   CONNECT: Establishes a network connection to the server.
    
	-   OPTIONS: Describes the communication options for the target resource. This method is used to retrieve information about the communication options available for a resource.
    
	-   TRACE: Performs a message loop-back test along the path to the target resource.
    
	-   PATCH: Applies partial modifications to a resource. This method is used to update only a portion of a resource, rather than replacing the entire resource.
    
	-  OPTIONS: Describes the communication options for the target resource. The OPTIONS method is used to describe the communication options for a resource, such as the supported methods, response formats, and request parameters.
    

Each of these methods performs a specific action on a specified resource and can return a different response based on the server implementation. Understanding the use of these methods is important for creating and consuming RESTful APIs.