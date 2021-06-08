# Javascript generator

In JavaScript, a regular function is executed based on the run-to-completion model. It cannot pause midway and then continues from where it paused.

## Example

```js
function foo() {
  console.log("I");
  console.log("cannot");
  console.log("pause");
}

foo();
// function executes top to bottom
// The only way to exit the foo() is by returning from it

// I
// cannot
// pause
```

```js
function* generate() {
  console.log("invoked 1st time");
  yield 1;
  console.log("invoked 2nd time");
  yield 2;
}

let gen = generate();
// A generator can pause midway and then continues from where it paused.
// returns a value and pauses the execution of the function.

console.log(gen);
// Object [Generator] {}

let result = gen.next();
console.log(result);
// invoked 1st time
// { value: 1, done: false }

result = gen.next();
console.log(result);
// invoked 2nd time
// { value: 2, done: false }

result = gen.next();
console.log(result);
// { value: undefined, done: true }
```

## Summary

- Generators are created by the generator function function\* f(){}.
- Generators do not execute its body immediately when they are invoked.
- Generators can pause midway and resumes their executions where they were paused. The yield statement pauses the execution of a generator and returns a value.
- Generators are iterable so you can use them with the for...of loop.

```js
for (const g of gen) {
    console.log(g);
}
Code language: JavaScript (javascript)

```

---

references
https://www.javascripttutorial.net/es6/javascript-generators/
