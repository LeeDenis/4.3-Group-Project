Deleting Resources

The DELETE request serves to wipe the target resource from the server. 
The DELETE request should result in a server response regarding the request.
Example request: 
	DELETE /directory/resource HTTP/1.1
	Accept: application/json
	Host: genericwebsitewithdirectoriesandsubdirectories.com
	Accept: application/vnd.api+json
Potential Responses:
    200 OK
    404 Not Found




Request Responses

HTTP request responses are attached to a three-digit code, which are divided up according to type: 
100-199: Informational responses
200-299: Successful responses
300-399: Redirects
400-499: Client errors
500-599: Server errors


Request Responses (100’s)

Responses in the 100’s simply provide further information:
100 Continue: 
-The response indicates that the request has no issues, and that the client can continue the request. Sometimes, the 100 response can mean the request is a prompt, indicating that the request is actually already successful, or to verify intent before completing the delete request.
102 Processing:
-This response indicates that the server already received the request and is currently processing it, but has not yet generated a response.


Request Responses (200’s)

Responses in the 200’s indicate a successful request:
200 OK:
-The request for deletion is successful. This response comes with metadata involving the deletion (contents of deleted directory, file type, etc.)
202 Accepted:
-The request for deletion has been accepted, but has not yet been processed by the time the server responds. This does not necessarily mean that the deletion will be successful.
204 No Content:
-The request for deletion is successful, but with no accompanying data. Example: an empty directory is deleted, so there is no metadata to report.


Request Responses (300’s)

Responses in the 300’s indicate that the request had to be redirected. 
300 Multiple Choices: 
-Indicates that the request has multiple potential responses. The client then chooses from the set of responses. Response 300 is rarely used due to a lack of standardized ways to choose one of the options.
301 Moved Permanently:
-Indicates that the request target has been moved to a different location, typically followed by information on where the target has been moved.
303 See Other:
-Indicates that the princess target is not at the requested location, but can be found at another castle URL.


Request Responses (400’s)

Responses in the 400’s indicate a client error, and that the client (such as the browser) cannot complete the request:
400 Bad Request:
-This indicates that the server couldn’t understand the request due to syntax, such as inputting letters in a number-only field. 
401 Unauthorized:
-This indicates  that the request has come from a user who has not yet been authenticated, or has failed the authentication process.
403 Forbidden: 
-This indicates that although the client has been authenticated, they don’t have the rights to the requested access.
404 Not Found:
-This indicates that the server cannot find the requested resource.


Request Responses (500’s)

Responses in the 500’s indicate errors on the server side.
500 Internal Server Error:
-Indicates an unexpected error, with no available details.
502 Bad Gateway:
-Indicates that the server was acting as an intermediary to an upstream server, and received an invalid response from it.
503 Service Unavailable:
-Indicates the same as 502, but that the upstream server is temporarily unable to handle the request, but is working otherwise.
504 Gateway Timeout: 
-Indicates that the server did not receive a response from its upstream server in time


Request Responses (418)

418 I’m a Teapot:
	-This response indicates that a significant number of programmers are nerds who like to to insert easter eggs and inside jokes into their work. 
	-This response refers to HTCPCP (Hyper Text Coffee Control Protocol) April Fools’ jokes from 1998 and 2014.
	-This response indicates that the server refuses to or cannot brew coffee because it is a teapot. 
