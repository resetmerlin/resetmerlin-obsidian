1. What is localStorage?

	-  localStorage is a JavaScript API for storing key-value pairs in the browser. It allows web pages to store data on the client side, which can be accessed later even if the user closes the browser or navigates away from the website. 

	- The data is stored in the browser's local storage and can be retrieved using JavaScript. The localStorage object is part of the Web Storage API, which also includes sessionStorage for storing data that is only available for the duration of the user's session.

	- localStorage is most commonly used for web applications that need to store data on the client side that can be accessed later, even if the user closes the browser or navigates away from the website.


2. When do u use localStorage?

	-   Saving user preferences or settings: For example, a web application might store the user's preferred theme or font size in localStorage so that it can be applied again the next time the user visits the site.
	    
	-   Storing form data: A web application might use localStorage to store form data so that the user can continue working on a form at a later time, even if they accidentally close the browser or navigate away from the page.
	    
	-   Caching data: A web application might use localStorage to store data that it has retrieved from an API so that it can be accessed later without needing to make another request.
	    
	-   Storing login credentials: A web application might use localStorage to store login credentials so that the user doesn't have to enter them again the next time they visit the site.

3. Methods
	1. setitem
	```js
// Saving data to localStorage
localStorage.setItem("key", "value");

```

	2. getiem
	```js
// Retrieving(되찾다) data from localStorage
const storedValue = localStorage.getItem("key");

console.log(storedValue); // logs "value"
```