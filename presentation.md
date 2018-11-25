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

# Attackers

- Java - Sun Microsystems
- VBScript - Microsoft
- ActionScript/Flash - Adobe
- Silverlight - Microsoft
- Dart - Google
- TypeScript - Microsoft

---

## ToDo App Comparison

|           | Angular | React   | Vue     | Lit-Elm | ES6     |
| --------- | ------- | ------- | ------- | ------- | ------- |
| LoC       | 807     | 218     | 245     | 291     | 236     |
| LoC JS    | 248     | 93      | 186     | 105/196 | 105/196 |
| Devel     | 3.61 MB | 1.58 MB | 1.65 MB | 114 kB  | 102 kB  |
| Optimized | 3.30 MB | 141 kB  | 89 kB   | 46 kB   | 32 kB   |
