# **Node.js - First Application**
A Node.js application consists of the following three important components:
- **Import required modules**: use the **require** directive to load Node.js modules
- **Create server**: a server which will listen to client's requests similiar to Apache HTTP server
- **Read request and return response**: the server created will read the HTTP request made by the client which can be a broswer or a console and return the response

## **Creating Node.js Application**
1. **Import Required Module**
Use the require directive to load the http module and store the returned HTTP instance into an http variable
```js
var http = require("http");
```
2. Create server
We use the created http instance and call http.createServer() method to create a server instance and then we bind it at port 8081 using the listen method associated with the server instance. Pass it a function with parameters request and response. Write the sample implementation to always return "Hello World"
```js
var http = require("http");

http.createServer(function (request, response) {
    // Send the HTTP header
    // HTTP Status: 200 : OK
    // Content Type: text/plain
    response.writeHead(200, {'Content-Type': 'text/plain'});

    // Send the response body as 'Hello World"
    reponse.end('Hello World\n');
}).listen(8081);

// Console will print the message
console.log('Server running at http://127.0.0.1:8081/');
```
The above code is enough to create an HTTP server which listens, i.e., waits for a request over 8081 port on the local machine.
3. Testing Request & Reponse
