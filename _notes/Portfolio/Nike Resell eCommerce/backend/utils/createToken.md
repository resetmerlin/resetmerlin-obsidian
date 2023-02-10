```js
import jwt from "jsonwebtoken";

  

const createToken = (id) => {

  return jwt.sign({ id }, process.env.JWT_SECRET, {

    expiresIn: "30d",

  });

};

  

export default createToken;
```

1. This function get id arugment and make into jwt token
2. This function will gonna export to the [[user controller]]