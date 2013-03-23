# node-uuid 
Generates UUIDs in javascript (https://github.com/broofa/node-uuid)

```javascript
var uuid = require('node-uuid');
console.log(uuid.v4());
```

# request
A module for simplifying HTTP requests (https://github.com/mikeal/request)

Below is a simple request that involves a redirect
```javascript
var request = require('request');
request('http://www.nodejs.org/api', function (error, response, body) {
  if (!error && response.statusCode == 200) {
    console.log(body) // Print the node api page
  }
})
```

* is much more terse
* follows redirects

request can easily pipe the response to file.

```javascript
var request = require('request');
request('http://google.com/doodle.png').pipe(fs.createWriteStream('doodle.png'))
```


```javascript
var request = require('request')
, rand = Math.floor(Math.random()*100000000).toString();

request(
  { method: 'PUT'
  , uri: 'http://mikeal.iriscouch.com/testjs/' + rand
  , multipart: 
    [ { 'content-type': 'application/json'
      ,  body: JSON.stringify({foo: 'bar', _attachments: {'message.txt': {follows: true, length: 18, 'content_type': 'text/plain' }}})
      }
    , { body: 'I am an attachment' }
    ] 
  }
, function (error, response, body) {
    if(response.statusCode == 201){
      console.log('document saved as: http://mikeal.iriscouch.com/testjs/'+ rand)
    } else {
      console.log('error: '+ response.statusCode)
      console.log(body)
    }
  }
 );
```
