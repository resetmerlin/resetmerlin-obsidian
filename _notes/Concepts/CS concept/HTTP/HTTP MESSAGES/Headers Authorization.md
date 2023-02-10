1. What is Authorization in header?
	- The "Authorization" header in an HTTP request is used to send authentication information to the server. The value of the "Authorization" header is typically set to a token, such as a JSON Web Token (JWT), that the server can use to identify the client making the request and authorize access to protected resources.

	- In a typical scenario, the client would first authenticate with the server, either by logging in or by using some other means of authentication.
	
	- Upon successful authentication, ***the server sends a JWT to the client in the form of an "Authorization" header. The client then includes this header with each subsequent request to the server, allowing the server to verify the client's identity and grant access to protected resources as needed.

	The format of the "Authorization" header typically looks like this:
```
Authorization: Bearer [JWT]
```
	Where "Bearer" is a string indicating the type of token being used, and "[JWT]" is the actual JSON Web Token.

1. Web security perspective
	- From a web security perspective, the use of the "Authorization" header and JSON Web Tokens (JWTs) is a common pattern for implementing authentication and authorization. 

	- JWTs allow for stateless authentication, which means that the server does not need to store any session information to keep track of the client's authentication status. Instead, the client sends the JWT with each request, and the server can validate the token to determine if the client is authorized to access the requested resource.

	- However, JWTs are only secure if they are properly implemented and managed. For example, if JWTs are not properly signed or encrypted, they can be easily forged or altered by an attacker, leading to security vulnerabilities. Additionally, if JWTs are not properly managed on the client side, such as properly storing and protecting them, they can be leaked or stolen, compromising the security of the system.
	
	- It's important to follow best practices for implementing JWTs and other security measures to ensure the security of a web application. This may include using encryption and signatures to protect JWTs, implementing secure storage and management of JWTs on the client side, and following established security standards such as the OWASP Top 10.