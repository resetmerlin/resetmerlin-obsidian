1. What is URLSearchParams?
	- In JavaScript, URLSearchParams is a built-in object that provides a way to work with the query string of a URL. It allows you to easily get and set the values of query parameters, and provides methods for common operations such as appending and deleting parameters. URLSearchParams can be used in the browser or in Node.js.
2. How to use?

```js

let searchParams = new URLSearchParams("q=URLUtils.searchParams&topic=api"); console.log(searchParams.has("q")); 
// true 
console.log(searchParams.get("q")); 
//"URLUtils.searchParams" 
console.log(searchParams.getAll("topic")); 
// ["api"] 
console.log(searchParams.toString()); 
// "q=URLUtils.searchParams&topic=api" 
console.log(searchParams.append("topic", "webdev"));
// "q=URLUtils.searchParams&topic=api&topic=webdev"
```