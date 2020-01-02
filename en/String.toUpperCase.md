TOPICS: String.toUpperCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toUpperCase()`

The **`toUpperCase()`** method returns the calling string value converted to uppercase (the value
will be converted to a string if it isn't one).

## Syntax

```javascript
str.toUpperCase()
```

**parameter**: No parameters

**Return value**: A new string representing the calling string converted to upper case.

### Exceptions

|  |  |
| :-- | :-- |
| `TypeError` | When called on `null` or `undefined`, for example, `String.toUpperCase.call(undefined)`.

## Description

The `toUpperCase()` method returns the value of the string converted to uppercase. This method does
not affect the value of the string itself since JavaScript strings are immutable.

## Examples

### Basic usage

```javascript
console.log('alphabet'.toUpperCase()); // 'ALPHABET'
```

### Conversion of non-string `this` values to strings

This method will convert any non-string value to a string, when you set its `this` to a value that
is not a string:

```javascript
const a = String.prototype.toUpperCase.call({
  toString: function toString() {
    return 'abcdef';
  }
});

const b = String.prototype.toUpperCase.call(true);

// prints out 'ABCDEF TRUE'.
console.log(a, b);
```
