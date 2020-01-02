TOPICS: String.trimLeft
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.trimLeft()`

The **`trimStart()`** method removes whitespace from the beginning of a string.
`trimLeft()` is an alias of this method.

## Syntax

```javascript
str.trimStart();
str.trimLeft();
```

**parameter**: No parameters

**Return value**: A new string representing the calling string stripped of whitespace from its
beginning (left end).

## Description

The `trimStart()` / `trimLeft()` methods return the string stripped of whitespace from its left end.
`trimLeft()` or `trimStart()` do not affect the value of the string itself.

### Aliasing

For consistency with functions like [`String.padStart`](/en/webfrontend/String.padStart) the
standard method name is `trimStart`. However, for web compatibility reasons, `trimLeft` remains as
an alias to `trimStart`. In some engines this means:

```javascript
String.prototype.trimLeft.name === "trimStart";
```

## Examples

### Using `trimStart()`

The following example displays the lowercase string `'foo  '`:

```javascript
var str = '   foo  ';

console.log(str.length); // 8

str = str.trimStart();
console.log(str.length); // 5
console.log(str);        // 'foo  '
```
