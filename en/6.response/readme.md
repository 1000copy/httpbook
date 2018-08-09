# Response Message

After the server executes the client request, it needs to respond to the client, telling if it is successful, and possibly preventing request results within the message body.

The response message consists of:

	Response = status line
	*(header CRLF)
	CRLF
	[message body]

##Status-Line

It consists of three fields: HTTP version, status code, and status description:

	Status-Line = HTTP-Version SPACE Status-Code SPACE Reason-Phrase CRLF

The state description is a content that is read by humans and is not important for processing logic.
The HTTP version, the status code directly affects how the client handles this response message. The status code is a three-digit number that is used to inform the client of the result of the request. The first digit is a category that indicates the type of status code. Use this number to divide the status code into five categories:

 - 1xx: Information. 
 - 2xx: Success. The request is successfully accepted or understood, or executed. Our common `200 OK` is within this category.
 - 3xx: Redirect - Further action is required to complete the request. Our common `301 Redirect` is within this category.
 - 4xx: Client error. The data submitted by the client is incorrect and cannot be understood or accepted. Our common `404 Not Found` is within this category.
 - 5xx: Server error. The error has occurred with the server, regardless of the client.

We also classify response messages into six categories based on the status code category. There are only two status codes in 1xx, but because they are relatively complex, they are split into two categories for explanation and understanding.

## message-body

Will be described lately

