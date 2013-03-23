# Files


## Writing
```javascript
var fs = require('fs');
fs.unlink('./file*.txt');

fs.writeFile('./file1.txt', 'Some text\n', function(err) {
  if (err) throw err;
  console.log('Wrote file1.txt');
}); 
```

### fs.writeFile(filename, data, [options], callback)
* writes text to a file
