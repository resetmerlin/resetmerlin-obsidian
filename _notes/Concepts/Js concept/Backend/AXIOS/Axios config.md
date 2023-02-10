1. What is config in Axios?
	ex: axios(url, config)
	- `config` is an optional configuration object that can be used to customize the request being made with Axios. The `config` object can include properties such as:

		1. `method`: The HTTP method to use for the request (e.g. `GET`, `POST`, etc.)

		2. `headers`: An object containing HTTP headers to send with the request

		3. `params`: An object or a URLSearchParams object with the request parameters to be appended to the URL

		4. `data`: The data to be sent as the request body. Only applicable for request methods 'PUT', 'POST', and 'PATCH'

		5. `baseURL`: A base URL to be prepended to the `url` argument for the request

		6. `timeout`: A timeout in milliseconds after which the request will be automatically cancelled

		7. `responseType`: The type of data that the server will respond with, such as `json`, `text`, or `blob`

