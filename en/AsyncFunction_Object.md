TOPICS:  AsyncFunction
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `AsyncFunction` Object

The `AsyncFunction` constructor creates a new async function object. In JavaScript,
every [asynchronous function](/en/webfrontend/async_function) is actually an `AsyncFunction` object.

Note that `AsyncFunction` is not a global object. It can be obtained with the following code:

```JavaScript
Object.getPrototypeOf(async function(){}).constructor
```

## Syntax

```JavaScript
new AsyncFunction([arg1[, arg2[, ...argN]],] functionBody)
```

### Parameters

| Parameters | Description |
| :-- | :-- |
|**`arg1, arg2, ... argN`**| Names to be used by the function as formal argument names. Each must be a string that corresponds to a valid JavaScript identifier or a list of such strings separated with a comma; for example `"x"`, `"theValue"`, or `"a,b"`.|
|**`functionBody`**| A string containing the JavaScript statements comprising the function definition.|

## Description

async function objects created with the `AsyncFunction` constructor are parsed when the function is created.
This is less efficient than declaring an async function with an async function expression
and calling it within your code, because such functions are parsed with the rest of the code.

All arguments passed to the function are treated as the names of the identifiers of the parameters
in the function to be created, in the order in which they are passed.

!!! warn "Note"
    async functions created with the AsyncFunction constructor do not create closures to
    their creation contexts; they are always created in the global scope.

When running them, they will only be able to access their own local variables and global ones,
not the ones from the scope in which the AsyncFunction constructor was called.

This is different from using eval with code for an async function expression.

Invoking the AsyncFunction constructor as a function (without using the
[new operator](/en/webfrontend/new_operator)) has the same effect as invoking it as a constructor.

## Properties

| Properties | Description |
| :-- | :-- |
|**`AsyncFunction.length`**|  The AsyncFunction constructor's length property (whose value is `1`).|
|**`AsyncFunction.prototype`**| Allows the addition of properties to all async function objects.|

## AsyncFunction prototype object

### AsyncFunction prototype Properties

| Properties | Description |
| :-- | :-- |
|**`AsyncFunction.constructor`**| The initial value is AsyncFunction.|
|**`AsyncFunction.prototype[@@toStringTag]`**| Returns "AsyncFunction".|

## AsyncFunction prototype instances

`AsyncFunction` instances inherit methods and properties from `AsyncFunction.prototype`.

As with all constructors,
you can change the constructor's prototype object to make changes to all `AsyncFunction` instances.

## Examples

### Creating an async function from an AsyncFunction constructor

```JavaScript
function resolveAfter2Seconds(x) {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve(x);
    }, 2000);
  });
}

let AsyncFunction = Object.getPrototypeOf(async function(){}).constructor

let a = new AsyncFunction('a',
                          'b',
                          'return await resolveAfter2Seconds(a) + await resolveAfter2Seconds(b);');

a(10, 20).then(v => {
  console.log(v); // prints 30 after 4 seconds
});
```
