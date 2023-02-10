```js
import mongoose from "mongoose";

  

const connectDatabase = async () => {

  try {

    const conn = await mongoose.connect(process.env.MONGO_URI);

    console.log(`MongoDB Connected   ${conn.connection.host}`.cyan.underline);

  } catch (error) {

    console.error(`Error: ${error.message}`.red.underline.bold);

    process.exit(1);

  }

};

```
  

export default connectDatabase;

1. Before Making Database

	 - We need to know what is a concept of  [[Asynchronous]] operation. Because what we will gonna do is to connect to the mongo database, which requires to use async operation.
	 
	 - so now we have to choose between [[Callback function]], [[Promises]], [[async & await]] to perform async operation. 

	- People recommend to use [[async & await]], so we will gonna use this now, moreover we will use try catch to catch error.
	
```js
const connectDatabase = async () => {

  try {

 
  } catch (error) {

  }

};
```


2. Import "mongoose" and await mongoose.connect
```js
import mongoose from "mongoose";

const connectDatabase = async () => {

  try {
    const conn = await mongoose.connect('mongodb+srv://Id:password@cluster0.nsxtukq.mongodb.net/filename?retryWrites=true&w=majority');
	 
  } catch (error) {

  }

};
```
	To prevent MongoDB URI leak, we will put the URI on the env file   

```js
    const conn = await mongoose.connect(process.env.MONGO_URI);
```

3. Handle try catch

	 Console.log() to check is monoDB connected or not. 

```js
//If MongoDB connected, 
  console.log(`MongoDB Connected   ${conn.connection.host}`.cyan.underline);

//If there is error,
 console.error(`Error: ${error.message}`.red.underline.bold);

    process.exit(1);
```

4. Result

	so result will be like this: 

```js
import mongoose from "mongoose";

  

const connectDatabase = async () => {

  try {

    const conn = await mongoose.connect(process.env.MONGO_URI);

    console.log(`MongoDB Connected   ${conn.connection.host}`.cyan.underline);

  } catch (error) {

    console.error(`Error: ${error.message}`.red.underline.bold);

    process.exit(1);

  }

};

  

export default connectDatabase;
```
	
	
After this, [[Server]] script will import this.
