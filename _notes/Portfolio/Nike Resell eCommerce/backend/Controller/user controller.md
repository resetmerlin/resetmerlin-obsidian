```js
import asyncHandler from "express-async-handler";
import User from "../models/userModel.js";
import createToken from "../utils/createToken.js";
// @desc Auth user & get token
// @route POST/api/products
// @access  Public
const authenticationUser = asyncHandler(async (req, res) => {
  const { email, password } = req.body;

  const user = await User.findOne({ email });
  if (user && (await user.matchPassword(password))) {
    res.json({
      _id: user._id,
      name: user.name,
      email: user.email,
      isAdmin: user.isAdmin,
      token: null,
    });
  } else {
    res.status(401);
    throw new Error("Invalid email of password");
  }
});



///@desc GEt user profile
// @route GET/api/user/profile
// @access  Private

const getClientProfile = asyncHandler(async (req, res) => {

  const user = await User.findById(req.user._id);

  if (user) {

    res.json({

      _id: user._id,

      name: user.name,

      email: user.email,

      isAdmin: user.isAdmin,

    });

  } else {

    res.status(404);

    throw new Error("User not found");

  }

});

  

export { authenticationUser, getClientProfile };
```




1. Beginning
	- This is a body data, and the way that we access that is to request body. So that will give us the data that sent in the body. ![[Pasted image 20230201204645.png]]
2. Explainaition: authenticationUser:
	1. After request the body, we use constructor method to get the email, password data from body.
	```js
	  const { email, password } = req.body;
```
	2.  We use findOne method to find email data from User schema([[User model]]).  
	```js 
  const user = await User.findOne({ email });
```
	3. Before proceeding explaination, we should look the code from [[User model]], we used mongoose methods to bcrypt the password.

	4. Now what we are doing is to find out if the to password is same or not(Cuz one of the password already bcrypted).

	5. If this hypothesis is true, server respon json data like this: 
	```js 
 if (user && (await user.matchPassword(password))) {
    res.json({
      _id: user._id,
      name: user.name,
      email: user.email,
      isAdmin: user.isAdmin,
      token: null,
    });
  } else {
    res.status(401);
    throw new Error("Invalid email of password");

  }
```
	the argument password is from  'const { email, password } = req.body;'. Client sent email, password to the server, and the server verifies it is true or not.
	
	6.  Last, we export to the [[User routes]].

**Result
- Success
![[Pasted image 20230202035316.png]]
- Fail
![[Pasted image 20230202035352.png]]
2. Explainaition: getClientProfile
	1. After putting the User id on the user variable, we will gonna check is user variable is true or not.
	```js
  const user = await User.findById(req.user._id);


  if (user) {} else {
    res.status(404);
    throw new Error("User not found");

  }
```
	2. If it is true, we get res.json data except the token
	```js
	if (user) {

    res.json({

      _id: user._id,

      name: user.name,

      email: user.email,

      isAdmin: user.isAdmin,

    });

  } else {

    res.status(404);

    throw new Error("User not found");

  }
```

	3. At last, we will gonna import this to [[User routes]].