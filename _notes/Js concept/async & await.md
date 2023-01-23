1. What is Async/await? 

	- Async/await is a more recent addition to JavaScript. It allows you to write asynchronous code that looks and behaves like synchronous code. 

	- The "async" keyword is used to define a function that returns a Promise, and the "await" keyword is used to pause the execution of the function until the Promise is resolved. This makes it easier to write and understand code that runs asynchronously.

	- Async/await allows you to write asynchronous code that behaves like synchronous code. It allows you to use the traditional control flow structures such as loops and if-else statements, while still taking advantage of the benefits of asynchronous programming. By using the await keyword, you can pause the execution of a function until a promise is resolved, and then continue to execute the rest of the function's statements. This way, you can write asynchronous code that is easy to understand and debug, just like synchronous code.


!! If u don't know concept of Async or Sync, look at this note. Double Click! to see close.

![[Js-promise.excalidraw]]



2. Example: 
	using async/await to perform an asynchronous API call

```js

async function getData() { 
try { 
	const response = await fetch('https://api.example.com/data'); 
	const data = await response.json(); 
	console.log(data); 
} catch (error) { 
	console.log(error); 
 } 
}


```
In this example, the `getData` function is defined as async, which means it returns a [[Promises]]. Inside the function, we use the `await` keyword to wait for the promise returned by the `fetch` function to resolve. Once the promise is resolved, the `response` variable is assigned the resolved value, which is the API response.