1. What is next()?
	 - `next` function is used to pass control to the next middleware function in the stack. Middleware functions are units of code that are executed in a specific order to perform some action, such as authentication, data processing, or error handling.

	 - The `next` function is typically passed as an argument to a middleware function, and it is used to indicate that the current middleware has finished executing and that control should be passed to the next middleware in the stack.

	- For example, in an Express.js application, you might have a middleware function that checks for a valid JSON Web Token (JWT) in the "Authorization" header of an HTTP request. If a valid JWT is found, the middleware would call `next` to pass control to the next middleware in the stack. If a valid JWT is not found, the middleware might return an error response instead of calling `next`.