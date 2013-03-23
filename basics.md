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

* _require - used to load modules. <br>
  * set of core modules included in the box
    * 



