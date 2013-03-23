# npm

node modules can be published in a public registry known as the npm (node package manager) registry located at (https://npmjs.org). users can then use the _npm_ command line interface (cli) included with node.js (https://npmjs.org/doc/) to install modules. npm will install all dependent modules as well.

## package.json
package.json plays a special role with npm in that it also contains dependent modules.

```javascript
{ 
  "name" : "foo",
  "dependencies" :
  { "foo" : "1.0.0 - 2.9999.9999"
  , "bar" : ">=1.0.2 <2.1.2"
  , "baz" : ">1.0.2 <=2.3.4"
  , "boo" : "2.0.1"
  , "qux" : "<1.0.0 || >=2.3.1 <2.4.5 || >=2.5.2 <3.0.0"
  , "asd" : "http://asdf.com/asdf.tar.gz"
  , "til" : "~1.2"
  , "elf" : "~1.2.3"
  , "two" : "2.x"
  , "thr" : "3.3.x"
  }
}
```


## Common npm commands
install: install a module. 
