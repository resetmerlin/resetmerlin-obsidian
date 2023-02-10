1. What is JWT?
	- JWT stands for JSON Web Token, and it is a compact, URL-safe means of transmitting information between parties as a JSON object.

	- JWTs are commonly used for authentication and authorization purposes, as they allow the server to securely transmit information to the client in the form of a token. Once a user logs in and is authenticated, the server sends a JWT to the client, which can then be used to make subsequent requests to protected routes. 

	- The client sends the JWT with each request, and the server can validate the token to ensure the user has the necessary permissions to access the requested resource. This allows for a stateless authentication process, where the server does not need to keep track of the client's authentication status.

It uses json web token to do te authorization
![[JWT.excalidraw]]

 More description is in this canvas
![[JWT example.excalidraw]]

