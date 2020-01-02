TOPICS: Error
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Error` Object

The `Error` constructor creates an error object.
Instances of `Error` objects are thrown when runtime errors occur.
The `Error` object can also be used as a base object for user-defined exceptions.
See below for standard built-in error types.

## Syntax

```JavaScript
new Error([message[, fileName[, lineNumber]]])
```

### Parameters

| Parameters | Description |
| :-- | :-- |
|**`message`**|A human-readable description of the error.|
|**`fileName`** *(Optional)*| The value for the `fileName` property on the created `Error` object. Defaults to the name of the file containing the code that called the `Error()` constructor. *(This API has not been standardied)*|
|**`lineNumber Optional`** *(Optional)*| The value for the `lineNumber` property on the created `Error` object. Defaults to the line number containing the `Error()` constructor invocation.*(This API has not been standardied)*|

## Description

Runtime errors result in new `Error` objects being created and thrown.

This page documents the use of the `Error` object itself and its use as a constructor function.
For a list of properties and methods inherited by `Error` instances, see `Error.prototype`.

### Used as a function

When `Error` is used like a function -- without [`new`](/en/webfrontend/new),
it will return an `Error` object.
Therefore, a mere call to Error will produce the same output that constructing an `Error` object
via the new keyword would.

```JavaScript
// this...
const x = Error('I was created using a function call!')

​​​​// ...has the same functionality as this.
const y = new Error('I was constructed via the "new" keyword!')
```

### Error types

Besides the generic Error constructor, there are seven other core error constructors in JavaScript.
For client-side exceptions, see [Exception handling statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#Exception_handling_statements).

| Error types | Description |
| :-- | :-- |
|**[`EvalError`](/en/webfrontend/EvalError)**|Creates an instance representing an error that occurs regarding the global function [`eval()`](/en/webfrontend/eval). |
|**[`InternalError`](/en/webfrontend/InternalError)**|Creates an instance representing an error that occurs when an internal error in the JavaScript engine is thrown. E.g. `"too much recursion"`.|
|**[`RangeError`](/en/webfrontend/RangeError)**|Creates an instance representing an error that occurs when a numeric variable or parameter is outside of its valid range.|
|**[`ReferenceError`](/en/webfrontend/ReferenceError)**|Creates an instance representing an error that occurs when de-referencing an invalid reference.|
|**[`SyntaxError`](/en/webfrontend/SyntaxError)**|Creates an instance representing a syntax error that occurs while parsing code in [`eval()`](/en/webfrontend/eval).|
|**[`TypeError`](/en/webfrontend/TypeError)**|Creates an instance representing an error that occurs when a variable or parameter is not of a valid type.|
|**[`URIError`](/en/webfrontend/URIError)**|Creates an instance representing an error that occurs when [`encodeURI()`](/en/webfrontend/encodeURI) or [`decodeURI()`](/en/webfrontend/decodeURI).|

## Properties

| Properties | Description |
| :-- | :-- |
|**`Error.prototype`**|Allows the addition of properties to `Error` instances.|

## Methods

The global `Error` object contains no methods of its own, however, it does inherit some methods
from the prototype chain.

## Error instances

All `Error` instances and instances of `non-generic errors` inherit from `Error.prototype`.
As with all constructor functions, you can use the prototype of the constructor to add properties or
methods to all instances created with that constructor.

### Standard properties

| properties | Description |
| :-- | :-- |
|**`Error.prototype.constructor`**|Specifies the function that created an instance's prototype.|
|**[`Error.message`](/en/webfrontend/Error.message)**|Error message.|
|**[`Error.name`](/en/webfrontend/Error.name)**|Error name.|

### Vendor-specific extensions

!!! warn "Non-standard"
    This feature is non-standard and is not on a standards track.
    Do not use it on production sites facing the Web: it will not work for every user.
    There may also be large incompatibilities between implementations and the behavior may change
    in the future.

(1) Microsoft

| Microsoft properties | Description |
| :-- | :-- |
|**[`Error.description`](/en/webfrontend/Error.description)**|Error description. Similar to message.|
|**[`Error.number`](/en/webfrontend/Error.number)**|Error number.|

(2) Mozilla

| Mozilla properties | Description |
| :-- | :-- |
|**[`Error.fileName`](/en/webfrontend/Error.fileName)**|Path to file that raised this error.|
|**[`Error.lineNumber`](/en/webfrontend/Error.lineNumber)**|Line number in file that raised this error.|
|**[`Error.columnNumber`](/en/webfrontend/Error.columnNumber)**|Column number in line that raised this error.|
|**[`Error.stack`](/en/webfrontend/Error.stack)**|Stack trace.|

### Standard Methods

| Methods | Description |
| :-- | :-- |
|**[`Error.toSource()`](/en/webfrontend/Error.toSource)**|Returns a string containing the source of the specified Error object; you can use this value to create a new object. Overrides the [`Object.toSource()`](/en/webfrontend/Object.toSource) method.|
|**[`Error.toString()`](/en/webfrontend/Error.toString)**|Returns a string representing the specified object. Overrides the [`Object.toString()`](/en/webfrontend/Object.toString) method.|

## Examples

### Throwing a generic error

Usually you create an `Error` object with the intention of raising it using the [`throw`](/en/webfrontend/throw)
keyword. You can handle the error using the [`try...catch`](/en/webfrontend/try...catch) construct:

```JavaScript
try {
  throw new Error('Whoops!')
} catch (e) {
  console.error(e.name + ': ' + e.message)
}
```

### Handling a specific error

You can choose to handle only specific error types by testing the error type with the error's
[`constructor`](/en/webfrontend/Object.constructor) property or,
if you're writing for modern JavaScript engines, [`instanceof`](/en/webfrontend/instanceof) keyword:

```JavaScript
try {
  foo.bar()
} catch (e) {
  if (e instanceof EvalError) {
    console.error(e.name + ': ' + e.message)
  } else if (e instanceof RangeError) {
    console.error(e.name + ': ' + e.message)
  }
  // ... etc
}
```

### Custom Error Types

You might want to define your own error types deriving from `Error` to be able to throw `new MyError()`
and use `instanceof MyError` to check the kind of error in the exception handler.
This results in cleaner and more consistent error handling code.

See ["What's a good way to extend Error in JavaScript?"](https://stackoverflow.com/questions/1382107/whats-a-good-way-to-extend-error-in-javascript)
on StackOverflow for an in-depth discussion.

(1) ES6 Custom Error Class

!!! warn "Note"
    Versions of Babel prior to 7 can handle CustomError class methods,
    but only when they are declared with Object.defineProperty().
    Otherwise, old versions of Babel and other transpilers will not correctly handle the following
    code without additional configuration.

!!! info ""
    Some browsers include the CustomError constructor in the stack trace when using ES2015 classes.

```JavaScript
class CustomError extends Error {
  constructor(foo = 'bar', ...params) {
    // Pass remaining arguments (including vendor specific ones) to parent constructor
    super(...params)

    // Maintains proper stack trace for where our error was thrown (only available on V8)
    if (Error.captureStackTrace) {
      Error.captureStackTrace(this, CustomError)
    }

    this.name = 'CustomError'
    // Custom debugging information
    this.foo = foo
    this.date = new Date()
  }
}

try {
  throw new CustomError('baz', 'bazMessage')
} catch(e) {
  console.error(e.name)    //CustomError
  console.error(e.foo)     //baz
  console.error(e.message) //bazMessage
  console.error(e.stack)   //stacktrace
}
```

(2) ES5 Custom Error Object

!!! warn ""
    All browsers include the CustomError constructor in the stack trace when using a prototypal declaration.

```JavaScript
function CustomError(foo, message, fileName, lineNumber) {
  var instance = new Error(message, fileName, lineNumber);
  instance.name = 'CustomError';
  instance.foo = foo;
  Object.setPrototypeOf(instance, Object.getPrototypeOf(this));
  if (Error.captureStackTrace) {
    Error.captureStackTrace(instance, CustomError);
  }
  return instance;
}

CustomError.prototype = Object.create(Error.prototype, {
  constructor: {
    value: Error,
    enumerable: false,
    writable: true,
    configurable: true
  }
});

if (Object.setPrototypeOf){
  Object.setPrototypeOf(CustomError, Error);
} else {
  CustomError.__proto__ = Error;
}

try {
  throw new CustomError('baz', 'bazMessage');
} catch(e){
  console.error(e.name); //CustomError
  console.error(e.foo); //baz
  console.error(e.message); //bazMessage
}
```
