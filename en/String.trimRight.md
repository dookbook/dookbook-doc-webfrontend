TOPICS: String.trimRight
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.trimRight()`

The **`trimEnd()`** method removes whitespace from the end of a string. `trimRight()` is an
alias of this method.

## Syntax

```javascript
str.trimEnd();
str.trimRight();
```

**parameter**: No parameters

**Return value**: A new string representing the calling string stripped of whitespace from
its (right) end.

## Description

The `trimEnd()` / `trimRight()` methods return the string stripped of whitespace from its right end.
`trimEnd()` or `trimRight()` do not affect the value of the string itself.

### Aliasing

For consistency with functions like [`String.padEnd`](/en/webfrontend/String.padEnd) the standard
method name is `trimEnd`. However, for web compatibility reasons, `trimRight` remains as an alias to
`trimEnd`. In some engines this means:

```javascript
String.prototype.trimRight.name === "trimEnd";
```

## Examples

### Using `trimEnd()`

The following example displays the lowercase string `'   foo'`:

```javascript
var str = '   foo  ';

console.log(str.length); // 8

str = str.trimEnd();
console.log(str.length); // 6
console.log(str);        // '   foo'
```
