# Making an HTTP request

```javascript
var http = require('http');

req = http.get('nodejs.org/api', onGet);
  .on('error', function(e) {
    console.log('problem with request: ' + e.message);
   }
);

function onGet(res) {
  res.on('data', function(chunk) {
    console.log('data:' + chunk);
  });
}
```

### http.get(options, callback)
Convenience method for doing a GET request.

* options - a uri or a hash specfying params like host, method, headers, etc.
* res - the response. 
* both req and res expose events. (http://nodejs.org/api/http.html#http_http_get_options_callback)
* _data_ is called when a chunk of data is received
* _error_ is called if any error error occurs whether DNS resolution, TCP level errors, or actual HTTP errors.

### Event emitters

* Many objects in node emit events, they are called _Emitters_
* Emitters are used for notifications vs callbacks which ae used for completion of executing async code.
* To add a listener use the on() method
* To remote listeners to an event use the removeListener method 

```javascript
req.on('error', function(e) {
  console.log('problem with request: ' + e.message);
});
```
### Authoring emitters

* Derive from EventEmitter
* call _emit_ to raise events.
* can be any number of args.

```javascript
var util = require("util");
var events = require("events");

function MyStream() {
    events.EventEmitter.call(this);
}

util.inherits(MyStream, events.EventEmitter);

MyStream.prototype.write = function(data) {
    this.emit("data", data);
}
```


