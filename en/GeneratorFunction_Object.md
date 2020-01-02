TOPICS: GeneratorFunction
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `GeneratorFunction` Object

The `GeneratorFunction` constructor creates a new [`generator function`](/en/webfrontend/function*) object.
In JavaScript every [`generator function`](/en/webfrontend/function*)
is actually a `GeneratorFunction` object.

Note that `GeneratorFunction` is not a global object.
It could be obtained by evaluating the following code.

```JavaScript
Object.getPrototypeOf(function*(){}).constructor
```

## Syntax

```JavaScript
new GeneratorFunction ([arg1[, arg2[, ...argN]],] functionBody)
```

### Parameters

| Parameters | Description |
| :-- | :-- |
|**`arg1, arg2, ... argN`**|Names to be used by the function as formal argument names. Each must be a string that corresponds to a valid JavaScript identifier or a list of such strings separated with a comma; for example `"x"`, `"theValue"`, or `"a,b"`.|
|**`functionBody`**|A string containing the JavaScript statements comprising the function definition.|

## Description

[`generator function`](/en/webfrontend/function*) objects created with the `GeneratorFunction` constructor
are parsed when the function is created. This is less efficient than declaring a generator function
with a [`function* expression`](/en/webfrontend/function*) and calling it within your code,
because such functions are parsed with the rest of the code.

All arguments passed to the function are treated as the names of the identifiers of the parameters
in the function to be created, in the order in which they are passed.

!!! warn "Note"
    [`generator function`](/en/webfrontend/function*) created with the `GeneratorFunction` constructor
    do not create closures to their creation contexts; they always are created in the global scope.
    When running them, they will only be able to access their own local variables and global ones,
    not the ones from the scope in which the `GeneratorFunction` constructor was called.
    This is different from using [`eval`](/en/webfrontend/eval) with code for a generator function expression.

Invoking the GeneratorFunction constructor as a function (without using the [`new operator`](/en/webfrontend/new))
has the same effect as invoking it as a constructor.

## Properties

| Properties | Description |
| :-- | :-- |
|**`GeneratorFunction.length`**|The `GeneratorFunction` constructor's `length` property whose value is `1`.|
|**`GeneratorFunction.prototype`**|Allows the addition of properties to all generator function objects.|

## GeneratorFunction prototype object

### prototype Properties

| Properties | Description |
| :-- | :-- |
|**`GeneratorFunction.constructor`**|The initial value is `GeneratorFunction`.|
|**`GeneratorFunction.prototype.prototype`**|The value is `GeneratorPrototype`.|

## GeneratorFunction instances

`GeneratorFunction` instances inherit methods and properties from `GeneratorFunction.prototype`.
As with all constructors, you can change the constructor's prototype object to make changes to
all `GeneratorFunction` instances.

## Examples

### Creating a generator function from a GeneratorFunction constructor

```JavaScript
var GeneratorFunction = Object.getPrototypeOf(function*(){}).constructor
var g = new GeneratorFunction('a', 'yield a * 2');
var iterator = g(10);
console.log(iterator.next().value); // 20
```
