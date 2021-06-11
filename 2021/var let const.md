# What is the difference between var, let and const

## Scoping rules

- Variables declared by `var` keyword are scoped to the immediate function body (hence the function scope)

- while let variables are scoped to the immediate enclosing block denoted by { } (hence the block scope).

> function scope is confusing and was one of the main sources of bugs in JavaScript.

### var - function scope

```js
var greeter = "hey hi";

function newFunction() {
  var hello = "hello";
}
console.log(hello); // error: hello is not defined
```

### let - block scope

```js
let greeting = "say Hi";
let times = 4;

if (times > 3) {
  let hello = "say Hello instead";
  console.log(hello); // "say Hello instead"
}
console.log(hello); // hello is not defined
```

### var variables can be re-declared

```js
var greeter = "hey hi";
var greeter = "say Hello instead";
```

Here is why var keyword is cumbersome

```js
var greeter = "hey hi";
var times = 4;

if (times > 3) {
  var greeter = "say Hello instead";
}

console.log(greeter); // "say Hello instead"
```

### let can be updated but not re-declared.

```js
let greeting = "say Hi";
let greeting = "say Hello instead"; // error: Identifier 'greeting' has already been declared
```

This is because both instances are treated as different variables since they have different scopes.

```js
let greeting = "say Hi";
if (true) {
  let greeting = "say Hello instead";
  console.log(greeting); // "say Hello instead"
}
console.log(greeting); // "say Hi"
```

## Hoisting of var

```js
console.log(greeter);
var greeter = "say hello";

// -->

var greeter;
console.log(greeter); // undefined
greeter = "say hello";
```
