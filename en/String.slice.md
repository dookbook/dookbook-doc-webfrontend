TOPICS: String.slice
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.slice()`

The **`slice()`** method extracts a section of a string and returns it as a new string, without
modifying the original string.

## Syntax

```javascript
str.slice(beginIndex[, endIndex])
```

| parameter | Description |
| :-- | :-- |
| `beginIndex` | The zero-based index at which to begin extraction. If negative, it is treated as `str.length + beginIndex`. (For example, if `beginIndex` is `-3` it is treated as `str.length - 3`.)<br>If `beginIndex` is greater than or equal to `str.length`, `slice()` returns an empty string. |
| `endIndex` Optional | The zero-based index before which to end extraction. The character at this index will not be included.<br>If `endIndex` is omitted, `slice()` extracts to the end of the string. If negative, it is treated as `str.length + endIndex`. (For example, if `endIndex` is `-3` it is treated as `str.length - 3`.) |

**Return value**: A new string containing the extracted section of the string.

## Description

`slice()` extracts the text from one string and returns a new string. Changes to the text in one
string do not affect the other string.

`slice()` extracts up to but not including `endIndex`. `str.slice(1, 4)` extracts the second
character through the fourth character (characters indexed `1`, `2`, and `3`).

As an example, `str.slice(2, -1)` extracts the third character through the second to last
character in the string.

## Examples

### Using `slice()` to create a new string

The following example uses `slice()` to create a new string.

```javascript
let str1 = 'The morning is upon us.', // the length of str1 is 23.
    str2 = str1.slice(1, 8),
    str3 = str1.slice(4, -2),
    str4 = str1.slice(12),
    str5 = str1.slice(30);
console.log(str2)  // OUTPUT: he morn
console.log(str3)  // OUTPUT: morning is upon u
console.log(str4)  // OUTPUT: is upon us.
console.log(str5)  // OUTPUT: ""
```

### Using `slice()` with negative indexes

The following example uses `slice()` with negative indexes.

```javascript
let str = 'The morning is upon us.'
str.slice(-3)      // returns 'us.'
str.slice(-3, -1)  // returns 'us'
str.slice(0, -1)   // returns 'The morning is upon us'
```

This example counts backwards from the end of the string by `11` to find the start index and
forwards from the start of the string by `16` to find the end index.

```javascript
console.log(str.slice(-11, 16)) // => "is u"
```

Here it counts forwards from the start by `11` to find the start index and backwards from the end by
`7` to find the end index.

```javascript
console.log(str.slice(11, -7)) // => " is u"
```

These arguments count backwards from the end by `5` to find the start index and backwards from the
end by `1` to find the end index.

```javascript
console.log(str.slice(-5, -1)) // => "n us"
```
