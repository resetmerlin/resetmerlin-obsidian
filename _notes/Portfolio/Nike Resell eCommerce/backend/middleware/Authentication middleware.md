```js
import jwt from "jsonwebtoken";
import User from "../models/userModel.js";
import asyncHandler from "express-async-handler";
const protection = asyncHandler(async (req, res, next) => {
  let token;
  if (
    req.headers.authorization &&
    req.headers.authorization.startsWith("Bearer")
  ) {
    try {
      token = req.headers.authorization.split(" ")[1];
      const decoded = jwt.verify(token, process.env.JWT_SECRET);
      console.log(decoded);
      next();
    } catch (error) {}
  }


  if (!token) {
    res.status(401);
    throw new Error("Not authorized, bo token");
  }

});


export { protection };
```

1. Authentication middlware?
	- The reason we are making authentication is to implement [[private routes]]. 
	- We use JWT to enhance the securities. => [[What is JWT]]?

2. Explaination


	1. First we should learn the meaning of [[Headers Authorization]]. After understanding concept of [[Headers Authorization]], we now proceed to code

	3. `req.headers.authorization` would give you the value of the "Authorization" header in the incoming HTTP request. This could be used in a server-side application, for example, to validate the JWT and determine if the client is authorized to access a protected resource.

	4. We make if statement to verify Authorization http request works.
	```js
	  if (
    req.headers.authorization &&
    req.headers.authorization.startsWith("Bearer")
  ) {
   
  }

```
	    req.headers.authorization.startsWith("Bearer") is to check HTTP header we request starts with 'Bearer'

	5. Once we received authorization header, we will gonna split it cuz the header looks like this: 'Bearer tokentokentoken'. We only want token, so we split a string based on the space between Bearer and token. Therefore we now able to get token by selecting as a 1 index.
	```js
      token = req.headers.authorization.split(" ")[1];
```

	
	 6. Next step is we will gonna decode the pure token. 
	```js
      const decoded = jwt.verify(token, process.env.JWT_SECRET);
```


	7. After decode, we will gonna await till User find decoded id, and use [[Select method]] to exclude from return value.
	```js
		 req.user = await User.findById(decoded.id).select("-password");
```

	8. try catch method to also handle error.

	```js
	 try {

      token = req.headers.authorization.split(" ")[1];
      const decoded = jwt.verify(token, process.env.JWT_SECRET);
      req.user = await User.findById(decoded.id).select("-password");

      next();

    } catch (error) {
      console.error(error);
      res.status(401);
      throw new Error("Not authorized, token failed");

    }
```

	- If u want the meaning of 401 status code, u can read it from [[Status code]]
	- Moreover, if u know the meaning of next(), u can read it from [[next()]]