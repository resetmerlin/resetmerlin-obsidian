1. What is a _request target_, usually a URL or the absolute path of the protocol, port, and domain are usually characterized by the request context. The format of this request target varies between different HTTP methods. It can be

	-   An absolute path, ultimately followed by a `'?'` and query string. This is the most common form, known as the _origin form_, and is used with `GET`, `POST`, `HEAD`, and `OPTIONS` methods.
	    -   `POST / HTTP/1.1`
	    -   `GET /background.png HTTP/1.0`
	    -   `HEAD /test.html?query=alibaba HTTP/1.1`
	    -   `OPTIONS /anypage.html HTTP/1.0`
- 
	-   A complete URL, known as the _absolute form_, is mostly used with `GET` when connected to a proxy. `GET https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages HTTP/1.1`

	-   The authority component of a URL, consisting of the domain name and optionally the port (prefixed by a `':'`), is called the _authority form_. It is only used with `CONNECT` when setting up an HTTP tunnel. `CONNECT developer.mozilla.org:80 HTTP/1.1`

	-   The _asterisk form_, a simple asterisk (`'*'`) is used with `OPTIONS`, representing the server as a whole. `OPTIONS * HTTP/1.1`