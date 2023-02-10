```js
import mongoose from "mongoose";

import bcrypt from "bcryptjs";

const userSchema = mongoose.Schema(

  {

    name: {

      type: String,

      required: true,

    },

    email: {

      type: String,

      required: true,

      unique: true,

    },

    password: {

      type: String,

      required: true,

    },

    isAdmin: {

      type: Boolean,

      required: true,

      default: false,

    },

  },

  {

    timestamps: true,

  }

);

userSchema.methods.matchPassword = async function (enteredPassword) {

  return await bcrypt.compare(enteredPassword, this.password);

};

const cyberUserModel = mongoose.model("User", userSchema);

  

export default cyberUserModel;
```

- In this code, we bcrypt password using custom method which is this:
```js
userSchema.methods.matchPassword = async function (enteredPassword) {

return await bcrypt.compare(enteredPassword, this.password);

};
```
	This code is a method defined on a Mongoose schema object named `userSchema`. The method is named `matchPassword` and it takes one argument, `enteredPassword`.

	The function uses the `bcrypt` library to compare the `enteredPassword` with the password stored in the current document, accessible via `this.password`. The `bcrypt.compare` function returns a Promise that resolves to a boolean indicating whether the two passwords match. The function returns the result of this comparison.