# Classes, Inheritance, Functional Programming


### Why would you want to run JavaScript code outside of a browser?
can use the File System API to access and manipulate the file system of an operating system. It gives the developer basic CRUD (Create, Read, Update, and Delete) operations on the file system. For security reasons, that cannot be done in browsers. Basically, JavaScript becomes more powerful.

### What is the difference between a module and a package?
A module is any file or directory in the node_modules directory that can be loaded by the Node.js require() function.

A package is a file or directory that is described by a package.json file. A package must contain a package.json file in order to be published to the npm registry. For more information on creating a package.json file, see “Creating a package.json file”.

**Note:** Since modules are not required to have a package.json file, not all modules are packages. Only modules that have a package.json file are also packages.


### What does the node package manager do?

 It is an online repository for the publishing of open-source Node.js projects; second, it is a command-line utility for interacting with said repository that aids in package installation, version management, and dependency management.

### Provide code snippets showing 3 different ways to export a function from a node module

1- Export Literals

```js
// file name Message.js
module.exports = 'Hello world';
```

```js
// file name app.js
var msg = require('./Messages.js');
console.log(msg);
```


2- Export Object

```js
// file name Message.js
exports.SimpleMessage = 'Hello world';
//or
module.exports.SimpleMessage = 'Hello world';
```

```js
// file name app.js
var msg = require('./Messages.js');

console.log(msg.SimpleMessage);
```


3- Export Function

```js
// file name Log.js
module.exports = function (msg) { 
    console.log(msg);
};
```

```js
// file name app.js
var msg = require('./Log.js');

msg('Hello World');
```

## Document the following Vocabulary Terms
Vocabulary Terms | Document 
--- | ---
ecosystem | is a set of software developers functioning as a unit and interacting with a shared market for software artefacts.
Node.js | open-source, cross-platform, JavaScript runtime environment that executes JavaScript code outside of a web browser.
V8 Engine | V8 extends JavaScript by adding additional features to preform lower-level operations as C++ does.
module | A module is any file or directory in the node_modules directory that can be loaded by the Node.js require() function.
package | A package is a file or directory that is described by a package.json file.
npm |  Is the largest ecosystem of open source libraries in the world.
server | A computer that provides data to other computers.
environment | et of processes and tools that are used to develop a source code or program.
interpreter | program that executes instructions written in a high-level language.
compiler | is a special program that processes statements written in a particular programming language and turns them into machine language or "code" that a computer's processor uses.