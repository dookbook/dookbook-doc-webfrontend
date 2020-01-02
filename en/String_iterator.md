TOPICS: String.[@@iterator]
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.[@@iterator]()`

The **`[@@iterator]()`** method returns a new `Iterator` object that iterates over the code points
of a String value, returning each code point as a String value.

## Syntax

```javascript
str[Symbol.iterator]
```

**parameter**: No parameters

**Return value**: A new `Iterator` object.

## Examples

### Using `[@@iterator]()`

```javascript
var str = 'A\uD835\uDC68';

var strIter = str[Symbol.iterator]();

console.log(strIter.next().value); // "A"
console.log(strIter.next().value); // "\uD835\uDC68"
```

### Using `[@@iterator]()` with `for..of`

```javascript
var str = 'A\uD835\uDC68B\uD835\uDC69C\uD835\uDC6A';

for (var v of str) {
  console.log(v);
}
// "A"
// "\uD835\uDC68"
// "B"
// "\uD835\uDC69"
// "C"
// "\uD835\uDC6A"
```
