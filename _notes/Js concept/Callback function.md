1. What is Callback function?

	-  In JavaScript, a callback function is a function that is passed as an argument to another function and is executed after some kind of event or operation has completed. The callback function is typically invoked asynchronously, which means that the parent function continues to run after the callback is called, allowing other code to execute in the meantime.

	- A callback function is a function that is passed as an argument to another function and is executed after some kind of event or operation has completed.

2. How callback functions are commonly used?

	1.  Event Handlers: Callbacks are often used as event handlers, such as when a button is clicked or a form is submitted. The callback function is executed when the event occurs.
		- example:  	
		```js
	
	// A button element
	var button = document.getElementById("myButton");
	
	// A callback function that will be executed when the button is clicked
	function handleClick() {
	  console.log("Button was clicked!");
	}
	
	// Register the callback as the click event handler for the button
	button.addEventListener("click", handleClick);
	
	// so in this code, the `handleClick` function is defined as the callback function
	```

	    
	2.  Timeout and Interval Functions: The setTimeout and setInterval functions take a callback as an argument, which is executed after a certain amount of time has passed.
		- example:
		```js
	function sayHello() { console.log("Hello!"); } 
	
	setTimeout(sayHello, 3000); 
	// This will call the sayHello function after 3 seconds
	
	// In this code, sayHello() is the callback function
	
	
	
```
	3.  Asynchronous API Calls: Many JavaScript APIs, such as the Fetch API, use callbacks to handle the results of asynchronous operations like network requests.
		- example:
		```js
	fetch("https://jsonplaceholder.typicode.com/posts") 
	.then(response => response.json())
	.then(data => { 
	// this function (data => { ... }) is a callback function.
	console.log(data); })
	.catch(error => { 
	// this function (error => { ... }) is a callback function. 
	console.error("Error:", error); });
```
	
	4.  Higher-Order Functions: Some JavaScript functions, such as the Array.prototype.forEach method, take a callback as an argument and use it to perform an operation on each element of an array.
		- example:
```js
	numbers.forEach(function(number) { 
	// this function (function(number) { ... }) is a callback function. console.log(number); });

```

