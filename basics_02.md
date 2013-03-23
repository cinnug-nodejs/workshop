# Making an HTTP request


```javascript
var http = require('http');
var util = require('util');

req = http.get({host:'nodejs.org', path:'/api'}, 
  function(res) {
		res.on('data', function(chunk) {
			console.log('data:' + chunk);
		});
	}
);

req.on('error', function(e) {
	console.log('problem with request: ' + e.message);
});
```


