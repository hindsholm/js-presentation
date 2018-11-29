<!-- .slide: data-background-image="img/JavaScript-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# JavaScript

Morten Hindsholm  
morten@hindsholm.dk

---

<!-- .slide: data-background-image="img/JavaScript-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# Agenda

1. History of JavaScript
2. Building Stuff
3. UI Frameworks and Libraries
4. Wrap-up

---

<!-- .slide: data-background-image="img/javascript.jpg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.3" -->

# History of JavaScript

----

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

----

## Functions as First-Class Objects

```javascript
var a = [1, 2, 3];                const a = [1, 2, 3];
a.forEach(function(e) {           a.forEach(e => {
  console.log(e);                   console.log(e);
});                               });
```

----

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

----

# Primitives vs Objects

## [Console](https://s3.amazonaws.com/mparsons/jsconsole/index.html)

Note:

```
typeof "abc"
typeof new String("abc")
```

----

<!-- .slide: data-background-image="img/ECMA-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.1" -->

# Nov. 1996: ECMAScript

> ... more than 300,000 JavaScript-enabled pages on the Internet today according to www.hotbot.com.

- ECMAScript 1: June 1997
    - based on Netscape Navigator 4
- ECMAScript 2: June 1998
    - alignment with ISO

----

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

----

# 2000-8: "ECMAScript 4" 

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

----

<!-- .slide: data-background-image="img/ajax.jpg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.1" -->

# 2005: AJAX

- XMLHttpRequest
- First introduced by Internet Explorer 5
    - as an ActiveX control(!)
- Later incorporated in the standard

----

# Dec. 2009: ECMAScript&nbsp;5

- Getters/setters
- Reserved words as property names
- New `Object` and `Array` methods <!-- .element: class="fragment highlight-red" -->
- New `Date` methods (`toISOString`, `now`, `toJSON`)
- Function `bind`
- JSON support
- Immutable global objects (`undefined`, `NaN`, `Infinity`)
- Strict mode <!-- .element: class="fragment highlight-red" -->
- Other minor changes

Note:

- Array methods improve certain functional patterns (map, reduce, filter, every, some). 
- Strict mode is preventing many common sources for errors. 
- JSON: a JavaScript-inspired data format that is now natively supported through JSON.stringify and JSON.parse

----

# June 2015:
# ECMAScript 2015 (ES6)

- Constants <!-- .element: class="fragment" -->
- Block scope <!-- .element: class="fragment" -->
- Arrow functions <!-- .element: class="fragment" -->
- Template literals <!-- .element: class="fragment" -->
- Destructuring assignment <!-- .element: class="fragment" -->
- Modules <!-- .element: class="fragment" -->
- Classes <!-- .element: class="fragment" -->
- Map & Set collections <!-- .element: class="fragment" -->
- Promises <!-- .element: class="fragment" -->
- ... <!-- .element: class="fragment" -->

----

# 2016 -

- June 2016: ECMAScript 2016 (ES7)
    - exponentiation operator (**)
- June 2017: ECMAScript 2017 (ES8)
    - `async` / `await`
- June 2018: ECMAScript 2017 (ES9)
    - rest/spread properties, asynchronous iteration

----

# JavaScript Assassination Attempts

- Java - Sun Microsystems <!-- .element: class="fragment" -->
- VBScript - Microsoft <!-- .element: class="fragment" -->
- ActionScript/Flash - Adobe <!-- .element: class="fragment" -->
- Silverlight - Microsoft <!-- .element: class="fragment" -->
- Dart - Google <!-- .element: class="fragment" -->
- TypeScript - Microsoft <!-- .element: class="fragment" -->

----

# JavaScript Engines

| Provider  | Engine         | Usage                            |
| --------- | -------------- | -------------------------------- |
| Opera     | Carakan        | Opera browser (until v. 15)      |
| Microsoft | Chakra         | Edge                             |
| Apple     | JavaScriptCore | Safari                           |
| Mozilla   | SpiderMonkey   | Firefox                          |
| Google    | V8             | Chrome, Chromium, Opera, Node.js |

---

<!-- .slide: data-background-image="img/building-stuff.jpg" data-background-size="fill" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# Building Stuff

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

<!-- .slide: data-background-image="img/modules.jpg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# Module Systems and Implementations

- Immediately-Invoked Function Expression ([IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE))
- CommonJS - Webpack
  - Node.js - Browserify
- Asynchronous Module Definition (AMD) - require.js, Dojo
- ES2015 - all major browsers
- All of the above - System.js 

Note:

- Client side implementations often package everything into one or two files
- [JavaScript Module Systems Showdown: CommonJS vs AMD vs ES2015](https://auth0.com/blog/javascript-module-systems-showdown/)

---

# Transpilers

Compiling some other language to JS

- Dart: OO language, drives Google Adwords
- ClojureScript: functional language, dynamic typing
- Scala.js: OO and functional
- CoffeeScript: "improved" JS, Ruby-like
- TypeScript: JS superset, static typing
- ... lots of others

Note:

- TS is not about types, it is about tooling

---

# Transpilers

Compiling JS to JS

- [Babel](https://babeljs.io/)
  - Using tomorrow's JavaScript today
  - Transform syntax
  - Polyfill features that are missing in your target environment
  - Used by React and others
- Traceur
  - same as Babel but inactive(?)

---

<!-- .slide: data-background-image="img/Npm-logo.svg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.1" -->

# npm

- Node Package Manager
- Open source packages in CommonJS format with metadata in JSON file
- World's largest collection: ~700.000 packages
- [Example](https://www.npmjs.com/package/react)

---

# Lots of Tools

- Lint
- Transpile
- Uglify
- Minify
- Optimize
- Pack
- Test
- ...

---

# Build Tools

- Grunt
  - ~6,500 plugins
- Gulp
  - JS build files, ~3,900 plugins, ...
- npm
  - install, build
- (Webpack)

----

<!-- .slide: data-background-image="img/grunt.png" data-background-size="30%" data-background-position="top left" data-background-repeat="no-repeat" data-background-opacity="0.3" -->

# Grunt Example

```
// Project configuration.
grunt.initConfig({
  pkg: grunt.file.readJSON('package.json'),
  uglify: {
    options: {
      banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
    },
    build: {
      src: 'src/<%= pkg.name %>.js',
      dest: 'build/<%= pkg.name %>.min.js'
    }
  }
});
// Load the plugin that provides the "uglify" task.
grunt.loadNpmTasks('grunt-contrib-uglify');
// Default task(s).
grunt.registerTask('default', ['uglify']);
```

----

<!-- .slide: data-background-image="img/gulp.png" data-background-size="20%" data-background-position="top left" data-background-repeat="no-repeat" data-background-opacity="0.3" -->

# Gulp Example

```
var gulp = require('gulp');
var concat = require('gulp-concat');
var sourcemaps = require('gulp-sourcemaps');

gulp.task('js', function() {
  return gulp.src('client/javascript/*.js')
    .pipe(sourcemaps.init())
    .pipe(concat('app.min.js'))
    .pipe(sourcemaps.write())
    .pipe(gulp.dest('build/js'))
});

gulp.task('css', function(){
  // ...
});

gulp.task('default', [ 'html', 'css', 'js' ]);
```

----

# npm Example

package.json:

```
{
  "name": "react-todo",
  "version": "0.1.0",
  "dependencies": {
    "react": "^16.4.1",
    "react-dom": "^16.4.1",
    "react-scripts": "1.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom"
  }
}
```

---

# UI Frameworks and Libraries

---

# jQuery

<!-- .slide: data-background-image="img/jQuery-logo.jpg" data-background-size="fill" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

- By far the most widely used JS library
- DOM traversal and manipulation
- Can lead to badly structured code
- Has to some extent become unnecessary because of DOM improvements

Note:

- As of June 2018, jQuery is used on 73% of the top 1 million websites, and by 22.4% of all websites (according to BuiltWith).

----

# jQuery Example

```
$.ajax({
  url: "/api/getWeather",
  data: {
    zipcode: 97201
  },
  success: function( result ) {
    $("#weather-temp").html("<strong>" + result + "</strong> degrees");
  }
});
```

---

# [ToDo App](http://localhost:8080/)

<!-- .slide: data-background-image="img/ToDoApp.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

Note:

- [I created the exact same app in React and Vue. Here are the differences.](https://medium.com/javascript-in-plain-english/i-created-the-exact-same-app-in-react-and-vue-here-are-the-differences-e9a1ae8077fd)

---

<!-- .slide: data-background-image="img/Angular-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# Angular

- 1st generation: AngularJS
- 2nd generation: Angular 2, 4, 5, 6, 7
  - TypeScript
  - Component-based
  - Modularity
  - Complete application framework
  - Progressive Web Apps
  - CLI

---

<!-- .slide: data-background-image="img/React-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# React

- UI Library
- Component-based
- Application state synchronized with views
- Uses proprietary JSX format
- Applications may need additional libraries
- CLI

---

<!-- .slide: data-background-image="img/Vue-logo.png" data-background-size="fill" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# Vue.js

- UI Library
- Component-based
- Application state synchronized with views
- Supports React's JSX format
- Applications may need additional libraries
- CLI

Note:

- Vue was created by Evan You after working for Google using AngularJS in a number of projects. He later summed up his thought process: "I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight."[6] Vue was originally released in February 2014. 

---

# Web Components

- **Custom Elements**  
  JS APIs that allow you to create custom elements.
- **Shadow DOM**  
  JS APIs for attaching a "shadow" DOM tree to an element.
- **HTML Templates**  
  HTML placeholder elements with markup that is not rendered.

*All standard HTML and ES6* <!-- .element: class="fragment" -->

----

# lit-html

Next-generation HTML Templates in JavaScript

```
import {html, render} from 'lit-html';

// A lit-html template uses the `html` template tag:
let sayHello = (name) => html`<h1>Hello ${name}</h1>`;

// It's rendered with the `render()` function:
render(sayHello('World'), document.body);

// And render only updates the data that changed, without VDOM diffing!
render(sayHello('Everyone'), document.body);
```

*Faster than React!* <!-- .element: class="fragment" -->

----

# lit-element

```
<script type="module">
  import {LitElement, html} from '@polymer/lit-element';

  class MyElement extends LitElement {

    static get properties() {
      return { mood: {type: String} };
    }

    constructor() {
      super();
      this.mood = '';
    }

    render() {
      return html`<style> .mood { color: green; } </style>
        Web Components are <span class="mood">${this.mood}</span>!`;
    }

  }

  customElements.define('my-element', MyElement);
</script>
<my-element mood="happy"></my-element>
```

---

<!-- .slide: data-background-image="img/jspm-logo.png" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.2" -->

# jspm

- Load npm packages with the native browser ES module loader
- Modules are all served as separate files over HTTP/2 with CDN edge caching.
- Far-future expires are provided for exact package versions for fast reloads.
- Packages are lazy-loaded and cached
- Version support

Note:

- HTTP/2 may eliminate the need for minifying and packing
- Using ES6 modules implies lazy-loading

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

<!-- .slide: data-background-image="img/wrapping-up.jpg" data-background-size="contain" data-background-repeat="no-repeat" data-background-opacity="0.1" -->

# Wrapping Up

- ECMAScript 2015 is a complete platform for client app development <!-- .element: class="fragment" -->
- If you really like static types, TypeScript is a nice alternative <!-- .element: class="fragment" -->
- Think twice about relying on a framework (and its dependencies) <!-- .element: class="fragment" -->

---

# Links

- [A Brief History of JavaScript](https://auth0.com/blog/a-brief-history-of-javascript/)
- [How it feels to learn JavaScript in 2016](https://hackernoon.com/how-it-feels-to-learn-javascript-in-2016-d3a717dd577f) :)
- [ECMAScript 6 compatibility table](https://kangax.github.io/compat-table/es6/)
- [A night experimenting with Lit-HTML…](https://medium.com/@lucamezzalira/a-night-experimenting-with-lit-html-585a8c69892a)
