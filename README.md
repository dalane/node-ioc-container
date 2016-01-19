# A Dependency Injection Container for Node.js Applications
A small dependency injection container for Node.js quickly cobbled together after spending a little bit of time using require statements and realising that I could end up in dependency hell pretty quickly. It was inspired by the Pimple PHP dependency injection container.

## Installing

Installation via NPM is recommended as follows.

```shell
npm install dalane-addiction
```

## Usage

Suggested approach is to create a file called "dependencies.js" and in it map all of the dependencies your project has.

**Note, this package is in development and not available on NPM yet.**

```javascript
// dependencies.js
var container = require('dalane-addiction');

container.add('foo', function () {
  var Foo = require('./path/to/foo');
  return new Foo();
});

container.add('bar', function () {
  // return a new Bar object that uses constructor injection for its Foo dependency
  var Bar = require('./path/to/bar');
  return new Bar(container.get('foo'));
});

module.exports = container;
```

**Note, this package is in development and not available on NPM yet.**
