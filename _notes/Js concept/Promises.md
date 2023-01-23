1. What is Promises

	- 비동기 작업이 맞이할 미래의 완료 혹은 실패와 그 결과 값을 나타냄
	
	- Promises in JavaScript are a way to handle asynchronous operations. They allow you to register callbacks that will be called when the operation completes, or if it fails. This makes it easy to write code that is executed only after a certain condition is met, such as a server response or a timer expiration.


	- Promises have three states:

		1. Pending: The initial state, the promise is neither fulfilled nor rejected

		2. Fulfilled: The operation completed successfully, and the promise has a resulting value.

		3.  Rejected: The operation failed, and the promise has a reason for the failure.


	- Promises are created using the `Promise` constructor, which takes a function called the "executor" as an argument. The executor function takes two arguments: `resolve` and `reject`. 

		1. `resolve` is used to fulfill the promise with a value

		2. `reject` is used to reject the promise with a reason.

2. Two main methods of Promises

	- Promises have two main methods, `then` and `catch`. 

		1. `then` is used to register a callback that will be called when the promise is fulfilled, and it takes one argument, which is the resulting value. 

		2. `catch` is used to register a callback that will be called when the promise is rejected, and it takes one argument, which is the error.

3. Example 1: Making HTTP request
```js

const axios = require('axios'); 
const getData = (url) => { 
return new Promise((resolve, reject) => { 
	axios 
		.get(url) 
		.then((response) => { 
		resolve(response.data); 
		})
		.catch((error) => { 
		reject(error); 
		}); 
	}); 
}; 

getData('https://jsonplaceholder.typicode.com/todos/1') 
	.then((data) => { 
	console.log(data); 
	}) 
	.catch((error) => { 
	console.log(`Error fetching data: ${error}`); 
	});


```

- In this example, a promise is returned by the `getData` function which makes an HTTP request to the specified url. If the request is successful, the promise is fulfilled with the response data, otherwise it is rejected with the error. The `then` method is used to handle the successful response and `catch` method is used to handle the error.

4. Summary

	- A JavaScript promise is an object that represents the eventual completion(최종 완료)  or failure of an asynchronous operation, and its resulting value. Promises provide a way to register callbacks to be called when the async operation completes, and they can be used to handle errors and exceptions.