
## Definitions

1. Web
	1. system of internet services that support specially formatted(in markup lang: HTML) documents(txt, video files).
	2. Web browser: apps helping us access web.
	3. communication between client & server => use specific app-lvl protocol(HTTP, FTP, SMTP, POP).

2. HTTP(Hyper Text Transfer Protocol)
	1. most popular app protocol used in web.
	2. client send req msg => server returns response (like a pull protocol).
	3. stateless protocol, current req doesn't know history of other req.
	4. ![](media/Pasted%20image%2020251101172758.png)

3. Browser 
	1. write an URL in browser bar => browser converts it to req msg + send to server
	2. HTTP server interrupt msg => send you the resource OR error msg
	3. ![](media/Pasted%20image%2020251101173047.png)

4. URLs(Uniform Resource Identifier)
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
	5. ![](media/Pasted%20image%2020251101202615.png)
	6. General Form:![](media/Pasted%20image%2020251101202839.png)
		1. protocol = scheme of URL
		2. username:pass => optional for server
		3. hostname:port => name of server w resource, port is optional
		4. path/filename => points to dir on the server/specific file on the dir
		5. query => contains form data for input to programs on server.
			- ? => start of query string			
			- & => adding more parameters to query
			- search=ruby => name/value pair
			- result=10 => name/value pair

## Breakdown