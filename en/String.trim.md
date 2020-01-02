TOPICS: String.trim
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.trim()`

The **`trim()`** method removes whitespace from both ends of a string. Whitespace in this context is
all the whitespace characters (space, tab, no-break space, etc.) and all the line terminator
characters (LF, CR, etc.).

## Syntax

```javascript
str.trim()
```

**parameter**: No parameters

**Return value**: A new string representing the calling string stripped of whitespace from both ends.

## Description

The `trim()` method returns the string stripped of whitespace from both ends. `trim()` does not
affect the value of the string itself.

## Examples

### Using `trim()`

The following example displays the lowercase string `'foo'`:

```javascript
var orig = '   foo  ';
console.log(orig.trim()); // 'foo'

// Another example of .trim() removing whitespace from just one side.

var orig = 'foo    ';
console.log(orig.trim()); // 'foo'
```

## Polyfill

Running the following code before any other code will create `trim()` if it's not natively available.

```javascript
if (!String.prototype.trim) {
  String.prototype.trim = function () {
    return this.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '');
  };
}
```
