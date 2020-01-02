TOPICS: String.repeat
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.repeat()`

The **`repeat()`** method constructs and returns a new string which contains the specified number of
copies of the string on which it was called, concatenated together.

## Syntax

```javascript
str.repeat(count)
```

| parameter | Description |
| :-- | :-- |
| `count` | An integer between `0` and `+Infinity`, indicating the number of times to repeat the string. |

**Return value**: A new string containing the specified number of copies of the given string.

### Exceptions

- `RangeError`: repeat count must be non-negative.
- `RangeError`: repeat count must be less than infinity and not overflow maximum string size.

## Examples

```javascript
'abc'.repeat(-1)    // RangeError
'abc'.repeat(0)     // ''
'abc'.repeat(1)     // 'abc'
'abc'.repeat(2)     // 'abcabc'
'abc'.repeat(3.5)   // 'abcabcabc' (count will be converted to integer)
'abc'.repeat(1/0)   // RangeError

({ toString: () => 'abc', repeat: String.prototype.repeat }).repeat(2)
// 'abcabc' (repeat() is a generic method)
```

## Polyfill

This method has been added to the ECMAScript 2015 specification and may not be available in all
JavaScript implementations yet. However, you can polyfill `String.prototype.repeat()` with the
following snippet:

```javascript
if (!String.prototype.repeat) {
  String.prototype.repeat = function(count) {
    'use strict';
    if (this == null)
      throw new TypeError('can\'t convert ' + this + ' to object');

    var str = '' + this;
    // To convert string to integer.
    count = +count;
    // Check NaN
    if (count != count)
      count = 0;

    if (count < 0)
      throw new RangeError('repeat count must be non-negative');

    if (count == Infinity)
      throw new RangeError('repeat count must be less than infinity');

    count = Math.floor(count);
    if (str.length == 0 || count == 0)
      return '';

    // Ensuring count is a 31-bit integer allows us to heavily optimize the
    // main part. But anyway, most current (August 2014) browsers can't handle
    // strings 1 << 28 chars or longer, so:
    if (str.length * count >= 1 << 28)
      throw new RangeError('repeat count must not overflow maximum string size');

    var maxCount = str.length * count;
    count = Math.floor(Math.log(count) / Math.log(2));
    while (count) {
       str += str;
       count--;
    }
    str += str.substring(0, maxCount - str.length);
    return str;
  }
}
```
