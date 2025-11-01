![](media/Pasted%20image%2020251101205015.png)
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


4. Absolute URLs(Uniform Resource Identifier)
	1. string of characters that uniquely identifies a resource(file, mail, msg)
	2. specifies:
		1. the location of file
		2. the protocol to access the server/mechanism of retrieving file.
		3. name of server.


5. Relative URLs
	1. type of URL specifies location of resource relative to current page.
	2. DOESN'T include: domain name, protocol 
	3. used to link resources in the same website wo specifying the whole URL.
	4. URL Vs. RURL![](media/Pasted%20image%2020251101211143.png)
		1. URL => always include domain name(http://www.), browser goes to the site
		2. RURL => only point to file/path, browser goes to that location on same site


6. URNs(Uniform Resource Name)
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
	2. HTTP server interrupt msg => send you the resource OR error msg
	3. ![](media/Pasted%20image%2020251101173047.png)
	4. 

