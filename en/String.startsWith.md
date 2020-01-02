TOPICS: String.startsWith
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.startsWith()`

The **`startsWith()`** method determines whether a string begins with the characters of a specified
string, returning `true` or `false` as appropriate.

## Syntax

```javascript
str.startsWith(searchString[, position])
```

| parameter | Description |
| :-- | :-- |
| `searchString` | The characters to be searched for at the start of this string. |
| `position` Optional | The position in this string at which to begin searching for `searchString`. Defaults to `0`. |

**Return value**: `true` if the given characters are found at the beginning of the string;
otherwise, `false`.

## Description

This method lets you determine whether or not a string begins with another string. This method is case-sensitive.

## Examples

### Using `startsWith()`

```javascript
//startswith
let str = 'To be, or not to be, that is the question.'

console.log(str.startsWith('To be'))          // true
console.log(str.startsWith('not to be'))      // false
console.log(str.startsWith('not to be', 10))  // true
```

## Polyfill

This method has been added to the ECMAScript 2015 specification and may not be available in all
JavaScript implementations yet. However, you can polyfill `String.prototype.startsWith()`
with the following snippet:

```javascript
if (!String.prototype.startsWith) {
    Object.defineProperty(String.prototype, 'startsWith', {
        value: function(search, rawPos) {
            var pos = rawPos > 0 ? rawPos|0 : 0;
            return this.substring(pos, pos + search.length) === search;
        }
    });
}
```

A more robust (fully ES2015 specification compliant), but less performant and compact, Polyfill is
available [on GitHub by Mathias Bynens](https://github.com/mathiasbynens/String.prototype.startsWith).
