# What is Javascript Proxy object

A JavaScript Proxy is an object that wraps another object (target) and intercepts the fundamental operations of the target object.

## How to use

```js
let proxy = new Proxy(target, handler);

const user = {
  firstName: "John",
  lastName: "Doe",
  email: "john.doe@example.com",
};

const handler = {
  get(target, property) {
    console.log(`Property ${property} has been read.`);
    return target[property];
  },
};

const proxyUser = new Proxy(user, handler);

console.log(proxyUser.firstName);
console.log(proxyUser.lastName);
// Property firstName has been read.
// John
// Property lastName has been read.
// Doe
```

## Proxy Traps

- get
- set
- apply
- construct – traps usage of the `new` operator
- getPrototypeOf – traps an internal call to `[[GetPrototypeOf]]`
- setPrototypeOf – traps a call to `Object.setPrototypeOf`
- isExtensible – traps a call to `Object.isExtensible`
- preventExtensions – traps a call to `Object.preventExtensions`
- getOwnPropertyDescriptor – traps a call to `Object.getOwnPropertyDescriptor`
  ...

---

### references

https://www.javascripttutorial.net/es6/javascript-proxy/
https://blog.bitsrc.io/a-practical-guide-to-es6-proxy-229079c3c2f0
https://hacks.mozilla.org/2015/07/es6-in-depth-proxies-and-reflect/
