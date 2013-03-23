# REPL
node has a repl.

```text
node
> console.log('Hello from node');
Hello from node
undefined
>
```

# HELLO WORLD

```js
var http = require('http');
http.createServer(function(req,res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello QCon\n');
}).listen(3000);
console.log('Listening on port 3000');
```

### Require - used to load modules. More [here](http://nodejs.org/api/)
Core modules are built in.
  * http/https: HTTP(s) server and clients
  * net: TCP servers and clients
  * fs: File I/O
  * child_process: spawn and manage child processes
  * globals: console, process args, env variables.

### http.createServer
Creates an HTTP server. Takes a callback which will be invoked on each request.
* _req, res_ - HTTP request/response object. 
* _res.writeHead_ - Write all HTTP headers
* _res.end_ - Write to the body and end.


