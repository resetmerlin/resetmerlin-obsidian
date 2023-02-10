 1. What is select method?

	 - The `select` method in Mongoose is a query modifier that is used to specify which fields of a document should be returned from a MongoDB database. By default, Mongoose will return all fields of a document, but you can use the `select` method to specify which fields to include or exclude.
	 
	 - The `select` method takes a string that specifies the fields to include or exclude. To include a field, simply list the field name in the string. To exclude a field, add a minus sign (`-`) in front of the field name.
	  
	 - For example, if you have a `User` model in Mongoose, you might use the `select` method to retrieve a user document while excluding their password:
	```js
	const user = await User.findById(userId).select("-password").exec();
```

	- This code uses the Mongoose `findById` method to retrieve a user with the given `userId`, and it uses the `select` method to exclude the `password` field from the returned document.

	- Note that the `select` method affects only the fields returned from the database, not the fields stored in the database. To exclude a field from being stored in the database, you would need to use the Mongoose schema definition to specify the field as `select: false`.