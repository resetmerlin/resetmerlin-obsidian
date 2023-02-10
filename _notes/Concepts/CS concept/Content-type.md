1. What is 'Content-type'?

	- Content-type header is an HTTP header that specifies the format of the request or response body. It's used to indicate the media type of the request or response payload, such as JSON, XML, plain text, HTML, etc.

	- The `Content-Type` header is essential for servers to correctly interpret the request payload, especially when it contains non-ASCII characters or binary data(0 or 1). It also helps clients to parse(정해진 포맷으로 작성된 프로그램을 분석하여 실행할 수 있는 내부 코드로 변경하는 것을 의미) the response and handle it appropriately.

	- The value of the `Content-Type` header is usually set to a [[MIME type]]

	- Setting the `Content-Type` header correctly is ***crucial for the proper functioning of a RESTful API, as it provides information to the server and client about the format of the data being exchanged.

2. Utilization 
	- You can utilize MIME types or Content-type in JavaScript code when sending HTTP requests or handling HTTP responses.

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



3. My questions:
![[Pasted image 20230210080050.png]]


![[Pasted image 20230210080441.png]]