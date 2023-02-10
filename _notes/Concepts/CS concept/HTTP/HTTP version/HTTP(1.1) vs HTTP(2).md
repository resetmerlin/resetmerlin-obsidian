1. Key diffences

	-   Binary format: HTTP/2 uses a binary format, as opposed to the text-based format of HTTP/1.1, which leads to more efficient and faster data transfer.
    
	-   Multiplexing: HTTP/2 enables multiple requests to be sent in parallel over a single connection, reducing the overhead of multiple connections and reducing latency. This is not possible in HTTP/1.1, which requires a new connection for each request.
    
	-   Server Push: HTTP/2 allows servers to proactively send assets to clients, reducing the number of round trips required for a complete page load. This is not possible in HTTP/1.1.
    
	-   Header compression: HTTP/2 includes built-in header compression, reducing the size of headers and increasing the efficiency of the data transfer.
    
	-   Prioritization: HTTP/2 allows clients to indicate the priority of requests, enabling the server to prioritize the most important requests first. This is not possible in HTTP/1.1.
    
	-   Flow control: HTTP/2 includes flow control mechanisms that prevent clients from overloading servers and help ensure a fair allocation of network resources.
    

In general, HTTP/2 is faster and more efficient than HTTP/1.1, and it provides a better user experience, especially on slower network connections. However, it also requires more computing resources and may not be necessary for simple websites or applications that do not require the additional features and performance benefits of HTTP/2.