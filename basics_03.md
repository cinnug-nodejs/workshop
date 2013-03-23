# Files
## Writing
```javascript
var fs = require('fs');
fs.writeFile('./file1.txt', 'Some text\n', function(err) {
  if (err) throw err;
  console.log('Wrote file1.txt');
}); 
```

### fs.writeFile(filename, data, [options], callback)
* writes text to a file
* options is a hash specifying addional params like encoding. default is utf8.

## Writing to a stream
```javascript
var fs = require('fs');
var os = fs.createWriteStream('./file2.txt');
os.write('Some text\n');
os.write('Some text\n');
console.log('Wrote file2.txt')
```

### fs.createWriteStream(path, [options]) (http://nodejs.org/api/fs.html#fs_fs_createwritestream_path_options)
* opens a file for streaming and returns a new stream.Writeable

### writable.write(chunk, [encoding], [callback])
* writes a chunk to the stream

## Reading
```javascript
var fs = require('fs');
fs.readFile('./file2.txt', 'utf8', function(err, data) {
  if (err) throw err;
  console.log(data);
});
```

### fs.readFile(filename, [options], callback)
* opens a file for reading and reads all the contents
* the callback is fired once when the reading is completed

## Reading a stream
```javascript
var fs = require('fs');
fs.createReadStream('./file2.txt', {encoding:'utf8',
  bufferSize:5}).
  on('data', function(chunk) {
    console.log('data:' + chunk);
  }).
  on('error', function(err) {
    throw err;
  });
```

### fs.createReadStream(path, [options])
* opens a file for reading and returns a new stream.Readable
* the _data_ event is fired for each chunk that s read.
* _error_ fies for any I/O related errors that occur



