TOPICS: Infinity
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Infinity` Object

The global `Infinity` property is a numeric value representing infinity.

| Property attributes of Infinity |  |
| :-- | :-- |
|**`writable`**|`false`|
|**`enumerable`**|`false`|
|**`configurable`**|`false`|

```JavaScript
const maxNumber = Math.pow(10, 1000); // max positive number

if (maxNumber === Infinity) {
  console.log("Let's call it Infinity!");
  // expected output: "Let's call it Infinity!"
}

console.log(1 / maxNumber);
// expected output: 0
```

## Description

`Infinity` is a property of the global object, or in other words, a variable in global scope.

The initial value of `Infinity` is [`Number.POSITIVE_INFINITY`](/en/webfrontend/Number.POSITIVE_INFINITY).
The value `Infinity` (positive infinity)
is greater than any other number. Mathematically, this value behaves the same as infinity;
for example, any positive number multiplied by `Infinity` equals `Infinity`, and any number divided
by `Infinity` equals `0`.

As defined by the ECMAScript 5 specification,
`Infinity` is read-only (implemented in JavaScript 1.8.5 / Firefox 4).

## Examples

```JavaScript
console.log(Infinity          ); /* Infinity */  
console.log(Infinity + 1      ); /* Infinity */  
console.log(Math.pow(10, 1000)); /* Infinity */  
console.log(Math.log(0)       ); /* -Infinity */  
console.log(1 / Infinity      ); /* 0 */
```
