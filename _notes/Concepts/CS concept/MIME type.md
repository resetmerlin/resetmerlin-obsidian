
1. What is MIME type?
	- MIME type (Media Type or Multipurpose Internet Mail Extensions) is a string identifier that specifies the format of a file or data.

	- It is a string that defines the format of the data. For example, `application/json` indicates that the data is in JSON format, `text/plain` indicates plain text, and `text/html` indicates HTML.

	- MIME types are used in HTTP headers and other communication protocols to indicate the type of data being transmitted.

	- MIME types are used by web browsers and servers to determine how to handle the data being transmitted. For example, if a server sends an HTTP response with a "Content-Type" header set to "text/html", the browser will interpret the response as an HTML document and render it accordingly.

2. MIME type consists of two parts:
	1. type: The type part indicates the general category of the data, such as "text", "image", "video", etc.
	2. subtype:  The subtype part provides more specific information about the format, such as "plain", "jpeg", "mp4", etc

	- Example: the MIME type "text/plain" indicates plain text, "image/jpeg" indicates a JPEG image, and "application/json" indicates data in JSON format.

So you now learned theories of MIME type. Next is how do u utilize it real world.


3. Utilization 
	- You can utilize MIME types in JavaScript code when sending HTTP requests or handling HTTP responses.

	- For example of using the Fetch API to send an HTTP POST request with a JSON payload and a "Content-Type" header set to "application/json"
	```js
fetch("https://example.com/api", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({ message: "Hello, World!" })
})
  .then(response => {
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    return response.json();
  })
  .then(data => {
    // Handle the response data
  })
  .catch(error => {
    // Handle any errors
  });

```
		In this example, the `fetch` function is used to send the request, with the `method`, `headers`, and `body` options specified. The `headers` option is used to set the "Content-Type" header to "application/json". The `body` option is used to specify the request payload, which is a JSON string.

		The `fetch` function returns a Promise that resolves to the `Response` object representing the response. The `then` method is used to handle the response, checking if the response is "ok" using the `ok` property, and if it is, parsing the response body as JSON using the `json` method.

		If there was an error sending the request or the response was not "ok", the error is caught and handled using the `catch` method.