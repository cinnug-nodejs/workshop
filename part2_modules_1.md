# Modules
node has a very simple module system. A module is a javascript file which exports functions or objects. modules can reference other modules.

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

