---
tags:
Date /Time: "{date} {time}"
title:
draft: true
---
http is a application layer protocol, that specify how one make a request of a web page and how one deliver the request. aka its the rules of engagement.
(File Transfer Protocol, Simple Mail Transfer Protocol for sending emails, the Data Distribution Service, Remote Desktop Protocol(RDP), XMPP  are all application layer protocols)

````
GET /HTTP/1.1
Host:cats.com
...etc
````
this is basically the request to get cats.com, to  get to cats.com(the request target) 
````
HTTP/1.1 200 OK/404 Not Found
Content-type: HTML
...
````
this is the response from cats.com(the host)

method request-target http-version is HTTP request line

- 200 OK
- 301 MOVED PERMANENTLY, the browser would redirect to a different URL permanently
- 302 FOUND, aka moving temporarily
- 401 UNAUTHORIZED
- 403 FORBBIDDEN the server existes but u dont have permission
-  404 NOT FOUND
- 500 Internal server