# HTTP Request

The HTTP protocol only allows the client to initiate a request, and only allows the server to return a response for the request. We have seen examples of requests, and now we specifically understand the composition of HTTP request messages. The request message includes a first line, a header fields, and a request body.


    Request = request line CRLF
    *Title CRLF
    CRLF
    [ message body ]

## Request Line

The request line consists of a request method, a request URL, and an HTTP version.

    Request-Line = Method SPACE Request-URI SPACE HTTP-Version CRLF

## Request method

HTTP / 1.1 support methods include:

    Method = "options"
    | "Get"
    | "POST"
    | "Put"
    | "Delete"
    | "Tracking"
    | "CONNECT"
    |Extension method
    Extension-method = token

The GET method is the only HTTP request method supported by the HTTP/0.9 protocol to indicate the delivery of a resource associated with a specified URL. Subsequently, for the purpose of optimization, the HEAD method was added; in order to support data submission to the server, the POST, PUT, DELETE methods were introduced,express respectively express a operation of update, create and delete specified resources. 

For any general purpose HTTP server, the GET, HEAD method must be implemented, and other methods are optional implemented. You can use the OPTIONS request method to query the list of request methods supported by a server resource.

That the header fields expressed by the text makes HTTP protocol easy to extend. As long as the client and the server are ready to do so, you can add the new request method you need. However, the type of content is something that this book will not discuss.

## Message Body

Will be described lately.

## Slightly summed up

- Request message of GET  indicates that I want to request a resource on the server specified by the URI.
- Request message of POST  means I want to update a resource specified by the URI
- Request message of PUT  means I want to create a resource specified by the URI
- Request message of DELETE  indicates that I want to delete a resource specified by a URI.
- Request message of HEAD  is the same as GET, but only returns the header part of the specified resource response without having to return the response body
- Request message of Option  is to query the list of target resource support s.
- Request message of TRACE  queries the intermediate nodes through which the target resource passes. Used for testing.
- Request message of CONNECT  establishes a tunnel to the server specified by the URI.
