<!-- .slide: data-background-image="img/JavaScript-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# JavaScript

Morten Hindsholm  
morten@hindsholm.dk

---

<!-- .slide: data-background-image="img/Netscape-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.15" -->


# 1995

![Influence](http://www.plantuml.com/plantuml/svg/PSknJiCm483XFKznOojHgJ0oe4gW3an8MLaE-vASQjzPvtCXF3qMKwJC__zTggDvosceDvQ2XXcoYeR5D1COtSagRU8NXjjisYI-Qb83DvJQ4ublhaWJjkHN5H_vb-3fl8a5OsIPuV4y7CQmKAOZd8pdnKylS7Z7Eux1kFWHdk7Q93YhO7hubBTLC7FeYjBKJTHlsPCFKrTV2m7BGiQE4cZudxf9DFdUZAiu_WmNajXo-WC0)

Mocha &rarr; LiveScript &rarr; JavaScript

Note:
- Mocha was to become a scripting language for the web. Simple, dynamic, and accessible to non-developers.
- Brendan Eich was contracted by Netscape Communications to develop a "Scheme for the browser".
- Java was not suited for the type of audience that would consume Mocha: scripters, amateurs, designers. Java was just too big, too enterprisy for the role.
- Python, Tcl, Scheme itself were all possible candidates.
- Lots of important decisions had to be made and very little time was available to make them. 
- "I’m not proud, but I’m happy that I chose Scheme-ish first-class functions and Self-ish (albeit singular) prototypes as the main ingredients. The Java influences, [...] the primitive vs. object distinction (e.g., string vs. String), were unfortunate."

---

## Functions as First-Class Objects

```javascript
var myFunction = function() {
  console.log('hello');
}
otherFunction(myFunction);
myFunction.property = '1';
```

---

## Functions as First-Class Objects

```javascript
var a = [1, 2, 3];                const a = [1, 2, 3];
a.forEach(function(e) {           a.forEach(e => {
  console.log(e);                   console.log(e);
});                               });
```

---

## `class` is Just Syntactical Sugar

```javascript
class User {                      function User(name) {
  constructor(name) {       
    this.name = name;               this.name = name;
  }                               }                         
  sayHi() {                       User.prototype.sayHi = function() {
    alert(this.name);               alert(this.name);
  }                               }                      
}
let user = new User("John");      let user = new User("John");
user.sayHi();                     user.sayHi();                   
```
JavaScript still uses prototype-based objects

---

# Primitives vs Objects

## [Console](https://s3.amazonaws.com/mparsons/jsconsole/index.html)

Note:

```
typeof "abc"
typeof new String("abc")
```

---

<!-- .slide: data-background-image="img/ECMA-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.1" -->

# Nov. 1996: ECMAScript

> ... more than 300,000 JavaScript-enabled pages on the Internet today according to www.hotbot.com.

- ECMAScript 1: June 1997
    - based on Netscape Navigator 4
- ECMAScript 2: June 1998
    - alignment with ISO

---

# Dec. 1999: ECMAScript&nbsp;3

- Regular expressions
- The do-while block
- Exceptions and the try/catch blocks
- More built-in functions for strings and arrays
- Formatting for numeric output
- The in and instanceof operators
- Much better error handling

Note:

This version of ECMAScript spread far and wide. It was supported by all major browsers at the time, and continued to be supported many years later.

---

# 2000-2008: "ECMAScript 4" 

<div class="container">
<div class="col">
Classes  
Interfaces  
Namespaces  
Packages  
Optional type annotations  
Optional static type checking  
Structural types  
Type definitions  
Multimethods  
Parameterized types  
Proper tail calls  
</div>
<div class="col">
Iterators  
Generators  
Instrospection  
Type discriminating exception handlers  
Constant bindings  
Proper block scoping  
Destructuring  
Succint function expressions  
Array comprehensions  
...
</div>
</div>

Note:

- Adobe, Mozilla, Opera, Microsoft and later Yahoo.
- Doug Crockford, an influential JavaScript developer, was the person sent by Yahoo 
- Crockford and Microsoft opposed the standard
- All in all, ECMAScript 4 took almost 8 years of development and was finally scrapped. A hard lesson for all who were involved.
- ActionScript (Flash) remains the closest look to what ECMAScript 4 could have been if it had been implemented by popular JavaScript engines

---

# 2005: AJAX

- XMLHttpRequest
- First introduced by Internet Explorer 5
    - as an ActiveX control(!)
- Later incorporated in the standard

---

# Dec. 2009: ECMAScript&nbsp;5

- Getter/setters
- Reserved words as property names
- New Object and Array methods
- New Date methods (toISOString, now, toJSON)
- Function bind
- JSON support
- Immutable global objects (undefined, NaN, Infinity)
- Strict mode
- Other minor changes

Note:

- Strict mode is preventing many common sources for errors. 
- Array methods improve certain functional patterns (map, reduce, filter, every, some). 
- JSON: a JavaScript-inspired data format that is now natively supported through JSON.stringify and JSON.parse

---

# June 2015:
# ECMAScript 2015 (ES6)

- Constants
- Block scope
- Arrow functions
- Template literals
- Destructuring assignment
- Modules
- Classes
- Map & Set collections
- Promises
- ...

---

- June 2016: ECMAScript 2016 (ES7)
    - exponentiation operator (**)
- June 2017: ECMAScript 2017 (ES8)
    - async / await
- June 2018: ECMAScript 2017 (ES9)
    - rest/spread properties, asynchronous iteration

---

# JS Attackers

- Java - Sun Microsystems
- VBScript - Microsoft
- ActionScript/Flash - Adobe
- Silverlight - Microsoft
- Dart - Google
- TypeScript - Microsoft

---

# JavaScript Engines

| Provider  | Engine         | Usage                       |
| --------- | -------------- | --------------------------- |
| Opera     | Carakan        | Opera browser (until v. 15) |
| Microsoft | Chakra         | Edge                        |
| Mozilla   | SpiderMonkey   | Firefox                     |
| Google    | V8             | Chrome, Node.js             |
| Apple     | JavaScriptCore | Safari                      |

---

<!-- .slide: data-background-image="img/Node.js-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.3" -->

# Node.js

- An asynchronous event driven JavaScript runtime designed to build scalable network applications.
- Created 2009, 13 years after server-side JavaScript
- Combines V8, an event loop and a low-level I/O API

----

# Node.js Example

```
// Synchronous
const fs = require('fs');                     
const data = fs.readFileSync('/file.md');   
console.log(data);                          
moreWork();  // will run after console.log                          

// Asynchronous
const fs = require('fs');
fs.readFile('/file.md', (err, data) => {
  if (err) throw err;
  console.log(data);
});
moreWork();  // will run before console.log
```

---

<!-- .slide: data-background-image="img/Npm-logo.svg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# npm

- Node Package Manager
- Open source packages in CommonJS format with metadata in JSON file
- World's largest collection: 700.000 packages
- [Example](https://www.npmjs.com/package/vue)

---

# ToDo App

- npm install
- npm start

---

## ToDo App Comparison

|           | Angular | React   | Vue     | Lit-Elm | ES6     |
| --------- | ------- | ------- | ------- | ------- | ------- |
| Disk      | 376 M   | 186 M   | 168 M   | 299 M   | 560 k   |
| LoC       | 807     | 218     | 245     | 291     | 236     |
| LoC JS    | 248     | 93      | 186     | 105/196 | 105/196 |
| Devel     | 3.61 M  | 1.58 M  | 1.65 M  | 114 k   | 102 k   |
| Optimized | 3.30 M  | 141 k   | 89 k    | 46 k    | 32 k    |

---

# Status on ES6

- A complete platform for ...
