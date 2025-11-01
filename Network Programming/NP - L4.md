![](media/Pasted%20image%2020251101205015.png)
## Definitions

1. Web
	1. system of internet services that support specially formatted(in markup lang: HTML) documents(txt, video files).
	2. Web browser: apps helping us access web.
	3. communication between client & server => use specific app-lvl protocol(HTTP, FTP, SMTP, POP).


2. HTTP(Hyper Text Transfer Protocol). ![](media/Pasted%20image%2020251101172758.png)
	1. most popular app protocol used in web.
	2. client send req msg => server returns response (like a pull protocol).
	3. stateless protocol, current req doesn't know history of other req.

	4. in IDLE state:
		1. just listens to IP add/Port in config for incoming requests
		2. when req arrive:
			1. server analyze msg header
			2. apply rules specified in config
			3. takes action

	5. HTTP + TCP/IP => port nums
		1. if not specified => default = 80 for HTTP
		2. if wanna specify => ![](media/Pasted%20image%2020251101214208.png)

	6. HTTP Specifications:
		- original HTTP/0.9 => transfer raw data
		1. HTTP/1.0 
			- allowing MIME-like msg 
			- open new connection/request
		2. HTTP/1.1 
			- reuse connections, browser can send many req over single connection
			- connection remains open till explicitly closed.
			- asynchronous(don't wait for response before sending 2nd,3rd req)
		3. HTTP/2.0 
			- improves protocol performance
			- exe compression auto of req/response
			- Add connection reset => if connection closed, auto open new one.

	7. MIME media types(Multipurpose Internet Mail Extension)
		- extension of e-mail protocol to send multimedia data through email, let people exchange different kinds of data(video, img, app, etc.)
		- describes fie content => so client sw


4. Browser 
	1. write an URL in browser bar => browser converts it to req msg + send to server
	2. HTTP server interrupt msg => send you the resource OR error msg
	3. ![](media/Pasted%20image%2020251101173047.png)


5. Absolute URLs(Uniform Resource Identifier)
	1. string of characters that uniquely identifies a resource(file, mail, msg)
	2. specifies:
		1. the location of file
		2. the protocol to access the server/mechanism of retrieving file.
		3. name of server.


6. Relative URLs
	1. type of URL specifies location of resource relative to current page.
	2. DOESN'T include: domain name, protocol 
	3. used to link resources in the same website wo specifying the whole URL.
	4. URL Vs. RURL![](media/Pasted%20image%2020251101211143.png)
		1. URL => always include domain name(http://www.), browser goes to the site
		2. RURL => only point to file/path, browser goes to that location on same site


7. URNs(Uniform Resource Name)
	1. only the name of resource
	2. starts with (urn)
	3. identifies resource without protocol/location.
	4. URN Vs. URL => city's name Vs. location on map.

## Breakdown

1. URLs(Uniform Resource Identifier)
	1. string of characters that uniquely identifies a resource(file, mail, msg)
	2. way to determine particular resource on particular location.
	3. specifies:
		1. the location of file
		2. the protocol to access the server/mechanism of retrieving file.
		3. name of server.
	4. Syntax: default port(80 for HTTP)![](media/Pasted%20image%2020251101202118.png)
		1. protocol: app-lvl protocol(HTTP, FTP) used by client & server
		2. host name: DNS name(www.xyz.com) or IP add(192.168.x.x)
		3. port: TCP port number that SERVER LISTED FOR REQUESTS.
		4. path-and-file-name: name+location of resource under the server base dir.
	5. General Form:![](media/Pasted%20image%2020251101202839.png)
		1. protocol = scheme of URL
		2. username:pass => optional for server
		3. hostname:port => name of server w resource, port is optional
		4. path/filename => points to dir on the server/specific file on the dir
		5. query => contains form data for input to programs on server.
			- ? => start of query string			
			- & => adding more parameters to query
			- search=ruby => name/value pair
			- result=10 => name/value pair
			- +query form ![](media/Pasted%20image%2020251101204555.png)
		6. fragment => specifies location within the resource
			- print here is fragment ![](media/Pasted%20image%2020251101204906.png)


2. Relative URLs(Absolute URL)
	1. type of URL specifies location of resource relative to current page.
	2. DOESN'T include: domain name, protocol 
	3. used to link resources in the same website wo specifying the whole URL.
	4. Syntax: ![](media/Pasted%20image%2020251101210924.png)
		1. linkhere.html => page u wanna link to it
		2. Click Me => name of link that page will display
	
	5. URL Vs. RURL![](media/Pasted%20image%2020251101211143.png)
		1. URL => always include domain name(http://www.), browser goes to the site
		2. RURL => only point to file/path, browser goes to that location on same site
	6. Mechanism:![](media/Pasted%20image%2020251101211645.png)


3. URNs(Uniform Resource Name)
	1. only the name of resource
	2. starts with (urn)
	3. identifies resource without protocol/location.
	4. URN Vs. URL => city's name Vs. location on map.
	5. General Form:![](media/Pasted%20image%2020251101205911.png)
		1. urn => prefix in ALL URNs
		2. namespace => name of collection of certain kind of resources
		3. resource_name => resource u want
		4. Ex.: ![](media/Pasted%20image%2020251101210042.png)


4. Browser 
	1. write an URL in browser bar => browser converts it to req msg + send to server
	2. HTTP server interrupt msg => send you the resource OR error msg![](media/Pasted%20image%2020251101173047.png)
	3. **Response message**![](media/Pasted%20image%2020251101212548.png)
	4. Browser receive the response msg => interpret msg => display contents according to media type(the content type in the bottom of response) (done in presentation layer)

