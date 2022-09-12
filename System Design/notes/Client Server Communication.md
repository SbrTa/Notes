# Client Server Communication
The majority of the communication on the web happens over HTTP. There are two modes of data transfer between the client and the server. 
  - HTTP PUSH
  - HTTP PULL

For every response, there has to be a request first. The client sends the request & the server responds with the data. 
This is the default mode of HTTP communication, called the HTTP PULL mechanism. 

In HTTP PUSH, the client sends the request for particular information to the server, just for the first time, and after that, 
the server keeps pushing the new updates to the client whenever they are available. 
There are multiple technologies involved in the HTTP Push based mechanism such as:
  - Long Polling
  - Web Sockets
  - Server Sent Event
