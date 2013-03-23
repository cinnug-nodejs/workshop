# Modules
node has a very simple module system (http://nodejs.org/api/modules.html). A module is a javascript file which exports functions or objects. modules can reference other modules.

## Authoring a module
Below is an example of a simple module

```javascript
//circle.js
var PI = Math.PI;

exports.area = function (r) {
  return PI * r * r;
};

exports.circumference = function (r) {
  return 2 * PI * r;
};
```
* exports is a special object returned from a module
* functions or other objects can be directly attached to the exports object.
* the exports object can also be completely replaced.

The circle module can then be consumed using require.

```javascript
var circle = require('./circle.js');
console.log( 'The area of a circle of radius 4 is '
  + circle.area(4));
```

## How modules are resolved?
* If the path is specified wih a relative path it will be loaded directly. 
* If it is not relative, node walks the file system relative to the current path to resolve modules.

Below is the algorithm for resolving non-relative modules. Assume the /root/app/server.js had a require('circle.js'), then node would look in the following folders.

/root/app/node_modules/circle.js <br>
/root/node_modules/circle.js <br>
/node_modules/circle.js <br>

## Side by side versioning
This model allows different modules to be loaded side by side in the same process.


