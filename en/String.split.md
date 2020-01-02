TOPICS: String.split
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.split()`

The **`split()`** method turns a [`String`](/en/webfrontend/String) into an array of strings, by
separating the string at each instance of a specified separator string.

## Syntax

```javascript
str.split([separator[, limit]])
```

| parameter | Description |
| :-- | :-- |
| `separator` Optional | The string where each split should occur. Can be a string or a regular expression.<br>1. If `separator` contains multiple characters, that entire character sequence must be found in order to split.<br>2. If `separator` is omitted or does not occur in `str`, the returned array contains one element consisting of the entire string.<br>3. If `separator` appears at the beginning or end of the string, or both, the array begins, ends, or both begins and ends, respectively, with an empty string.<br>4. If `separator` is an empty string (`""`), str is converted to an array of each of its UTF-16 "`characters`".<br><br>**Warning**: When the empty string (`""`) is used as a separator, the string is not split by user-perceived characters ([grapheme clusters](https://unicode.org/reports/tr29/#Grapheme_Cluster_Boundaries)) or unicode characters (codepoints), but by UTF-16 codeunits. This destroys [surrogate pairs](http://unicode.org/faq/utf_bom.html#utf16-2). See “How do you get a string to a character array in JavaScript?” on StackOverflow. |
| `limit` Optional | A non-negative integer limiting the number of splits. If provided, splits the string at each occurrence of the specified `separator`, but stops when `limit` entries have been placed in the array. Any leftover text is not included in the array at all.<br>1. The array may contain fewer entries than `limit` if the end of the string is reached before the `limit` is reached.<br>2. If `limit` is `0`, no splitting is performed. |

**Return value**: An `Array` of strings, split at each point where the `separator` occurs in the
given string.

## Description

When found, `separator` is removed from the string and the substrings are returned in an array.

If `separator` is a regular expression with capturing parentheses, then each time `separator` matches,
the results (including any undefined results) of the capturing parentheses are spliced into
the output array.

The separator is an array

!!! warn "Note"
    if the separator is an array, then that Array is coerced to a String and used as a separator.

## Examples

### Using `split()`

!!! warn "Note"
    When the string is empty, `split()` returns an array containing one empty string, rather than an
    empty array. If the string and separator are both empty strings, an empty array is returned.

```javascript
const myString = ''
const splits = myString.split()

console.log(splits)

// ↪ [""]
```

The following example defines a function that splits a string into an array of strings using the
specified separator. After splitting the string, the function logs messages indicating the original
string (before the split), the separator used, the number of elements in the array, and the
individual array elements.

```javascript
function splitString(stringToSplit, separator) {
  const arrayOfStrings = stringToSplit.split(separator)

  console.log('The original string is: ', stringToSplit)
  console.log('The separator is: ', separator)
  console.log('The array has ', arrayOfStrings.length, ' elements: ', arrayOfStrings.join(' / '))
}

const tempestString = 'Oh brave new world that has such people in it.'
const monthString = 'Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec'

const space = ' '
const comma = ','

splitString(tempestString, space)
splitString(tempestString)
splitString(monthString, comma)
```

This example produces the following output:

```javascript
The original string is: "Oh brave new world that has such people in it."
The separator is: " "
The array has 10 elements: Oh / brave / new / world / that / has / such / people / in / it.

The original string is: "Oh brave new world that has such people in it."
The separator is: "undefined"
The array has 1 elements: Oh brave new world that has such people in it.

The original string is: "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec"
The separator is: ","
The array has 12 elements: Jan / Feb / Mar / Apr / May / Jun / Jul / Aug / Sep / Oct / Nov / Dec
```

### Removing spaces from a string

In the following example, `split()` looks for zero or more spaces, followed by a semicolon, followed
by zero or more spaces—and, when found, removes the spaces and the semicolon from the string.
`nameList` is the array returned as a result of `split()`.

```javascript
const names = 'Harry Trump ;Fred Barney; Helen Rigby ; Bill Abel ;Chris Hand '

console.log(names)

const re = /\s*(?:;|$)\s*/
const nameList = names.split(re)

console.log(nameList)
```

This logs two lines; the first line logs the original string, and the second line logs the
resulting array.

```javascript
Harry Trump ;Fred Barney; Helen Rigby ; Bill Abel ;Chris Hand
[ "Harry Trump", "Fred Barney", "Helen Rigby", "Bill Abel", "Chris Hand", "" ]
```

### Returning a limited number of splits

In the following example, `split()` looks for spaces in a string and returns the first 3
splits that it finds.

```javascript
const myString = 'Hello World. How are you doing?'
const splits = myString.split(' ', 3)

console.log(splits)
```

This script displays the following:

```javascript
["Hello", "World.", "How"]
```

Splitting with a `RegExp` to include parts of the separator in the result

If `separator` is a regular expression that contains capturing parentheses `()`, matched results are
included in the array.

```javascript
const myString = 'Hello 1 word. Sentence number 2.'
const splits = myString.split(/(\d)/)

console.log(splits)
```

This script displays the following:

```javascript
[ "Hello ", "1", " word. Sentence number ", "2", "." ]
```

### Reversing a String using `split()`

This is not a robust way to reverse a string:

```javascript
const str = 'asdfghjkl'
const strReverse = str.split('').reverse().join('')
// 'lkjhgfdsa'

// split() returns an array on which reverse() and join() can be applied
```

It doesn't work if the string contains grapheme clusters, even when using a unicode-aware split
(use for example [esrever](https://github.com/mathiasbynens/esrever) instead).

```javascript
const str = 'résumé'
const strReverse = str.split(/(?:)/u).reverse().join('')
// => "́emuśer"
```

**Bonus**: use `===` operator to test if the original string was a palindrome.
