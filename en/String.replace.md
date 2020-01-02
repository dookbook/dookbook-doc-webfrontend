TOPICS: String.replace
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.replace()`

The **`replace()`** method returns a new string with some or all matches of a `pattern` replaced by
a `replacement`. The `pattern` can be a string or a `RegExp`, and the `replacement` can be a string
or a function to be called for each match. If `pattern` is a string, only the first occurrence
will be replaced.

The original string is left unchanged.

## Syntax

```javascript
var newStr = str.replace(regexp|substr, newSubstr|function)
```

| parameter | Description |
| :-- | :-- |
| `regexp` (pattern) | A `RegExp` object or literal. The match or matches are replaced with `newSubStr` or the value returned by the specified `function`. |
| `substr` (pattern) | A `String` that is to be replaced by `newSubStr`. It is treated as a verbatim string and is not interpreted as a regular expression. Only the first occurrence will be replaced. |
| `newSubStr` (replacement) | The `String` that replaces the substring specified by the specified `regexp` or `substr` parameter. A number of special replacement patterns are supported; see the "Specifying a string as a parameter" section below. |
| `function` (replacement) | A function to be invoked to create the new substring to be used to replace the matches to the given `regexp` or `substr`. The arguments supplied to this function are described in the "Specifying a function as a parameter" section below. |

**Return value**: A new string with some or all matches of a pattern replaced by a replacement.

## Description

This method does not change the [`String`](/en/webfrontend/String) object it is called on.
It simply returns a new string.

To perform a global search and replace, include the `g` switch in the regular expression.

### Specifying a string as a parameter

The replacement string can include the following special replacement patterns:

| Pattern | Inserts |
| :-- | :-- |
| `$$` | Inserts a `"$"`.
| `$&` | Inserts the matched substring.
| ``$` `` | Inserts the portion of the string that precedes the matched substring.
| `$'` | Inserts the portion of the string that follows the matched substring.
| `$n`| Where `n` is a positive integer less than 100, inserts the nth parenthesized submatch string, provided the first argument was a `RegExp` object. Note that this is 1-indexed. |

### Specifying a function as a parameter

You can specify a function as the second parameter. In this case, the function will be invoked after
the match has been performed. The function's result (return value) will be used as the replacement
string. (Note: the above-mentioned special replacement patterns do not apply in this case.) Note
that the function will be invoked multiple times for each full match to be replaced if the regular
expression in the first parameter is global.

The arguments to the function are as follows:

| **Possible name** | **Supplied value** |
| :-- | :-- |
| `match` | The matched substring. (Corresponds to `$&` above.) |
| `p1, p2, ...` | The nth string found by a parenthesized capture group, provided the first argument to `replace()` was a `RegExp` object. (Corresponds to `$1`, `$2`, etc. above.) For example, if `/(\a+)(\b+)/`, was given, `p1` is the match for `\a+`, and p2 for `\b+`.
| `offset` | The offset of the matched substring within the whole string being examined. (For example, if the whole string was '`abcd`', and the matched substring was '`bc`', then this argument will be `1`.)
| `string` | The whole string being examined.

(The exact number of arguments will depend on whether the first argument was a `RegExp` object and,
if so, how many parenthesized submatches it specifies.)

The following example will set `newString` to `'abc - 12345 - #$*%'`:

```javascript
function replacer(match, p1, p2, p3, offset, string) {
  // p1 is nondigits, p2 digits, and p3 non-alphanumerics
  return [p1, p2, p3].join(' - ');
}
var newString = 'abc12345#$*%'.replace(/([^\d]*)(\d*)([^\w]*)/, replacer);
console.log(newString);  // abc - 12345 - #$*%
```

## Examples

### Defining the regular expression in `replace()`

In the following example, the regular expression is defined in `replace()` and includes the
ignore case flag.

```javascript
var str = 'Twas the night before Xmas...';
var newstr = str.replace(/xmas/i, 'Christmas');
console.log(newstr);  // Twas the night before Christmas...
```

This logs 'Twas the night before Christmas...'

### Using global and ignore with `replace()`

Global replace can only be done with a regular expression. In the following example, the regular
expression includes the global and ignore case flags which permits `replace()` to replace each
occurrence of 'apples' in the string with 'oranges'.

```javascript
var re = /apples/gi;
var str = 'Apples are round, and apples are juicy.';
var newstr = str.replace(re, 'oranges');
console.log(newstr);  // oranges are round, and oranges are juicy.
```

This logs 'oranges are round, and oranges are juicy'.

### Switching words in a string

The following script switches the words in the string. For the replacement text, the script uses
the `$1` and `$2` replacement patterns.

```javascript
var re = /(\w+)\s(\w+)/;
var str = 'John Smith';
var newstr = str.replace(re, '$2, $1');
console.log(newstr);  // Smith, John
```

This logs 'Smith, John'.

### Using an inline function that modifies the matched characters

In this example, all occurrences of capital letters in the string are converted to lower case, and a
hyphen is inserted just before the match location. The important thing here is that additional
operations are needed on the matched item before it is given back as a replacement.

The replacement function accepts the matched snippet as its parameter, and uses it to transform the
case and concatenate the hyphen before returning.

```javascript
function styleHyphenFormat(propertyName) {
  function upperToHyphenLower(match, offset, string) {
    return (offset > 0 ? '-' : '') + match.toLowerCase();
  }
  return propertyName.replace(/[A-Z]/g, upperToHyphenLower);
}
```

Given `styleHyphenFormat('borderTop')`, this returns '`border-top`'.

Because we want to further transform the result of the match before the final substitution is made,
we must use a function. This forces the evaluation of the match prior to the [`toLowerCase()`](/en/webfrontend/String.toLowerCase)
method. If we had tried to do this using the match without a function, the [`toLowerCase()`](/en/webfrontend/String.toLowerCase)
would have no effect.

```javascript
var newString = propertyName.replace(/[A-Z]/g, '-' + '$&'.toLowerCase());  // won't work
```

This is because `'$&'.toLowerCase()` would be evaluated first as a string literal (resulting in the
same `'$&'`) before using the characters as a pattern.

### Replacing a Fahrenheit degree with its Celsius equivalent

The following example replaces a Fahrenheit degree with its equivalent Celsius degree. The
Fahrenheit degree should be a number ending with `F`. The function returns the Celsius number ending
with `C`. For example, if the input number is `212F`, the function returns `100C`. If the number is 0F,
the function returns `-17.77777777777778C`.

The regular expression `test` checks for any number that ends with F. The number of Fahrenheit
degree is accessible to the function through its second parameter, `p1`. The function sets the
Celsius number based on the Fahrenheit degree passed in a string to the `f2c()` function. `f2c()`
then returns the Celsius number. This function approximates Perl's `s///e` flag.

```javascript
function f2c(x) {
  function convert(str, p1, offset, s) {
    return ((p1 - 32) * 5/9) + 'C';
  }
  var s = String(x);
  var test = /(-?\d+(?:\.\d*)?)F\b/g;
  return s.replace(test, convert);
}
```

Use an inline function with a regular expression to avoid for loops

The following example takes a string pattern and converts it into an array of objects.

Input:

A string made out of the characters `x`, `-` and `_`

```javascript
x-x_
x---x---x---x---
x-xxx-xx-x-
x_x_x___x___x___
```

Output:

An array of objects. An `'x'` denotes an `'on'` state, a `'-'` (hyphen) denotes an `'off'` state and
an `'_'` (underscore) denotes the length of an `'on'` state.

```javascript
[
  { on: true, length: 1 },
  { on: false, length: 1 },
  { on: true, length: 2 }
  ...
]
```

Snippet:

```javascript
var str = 'x-x_';
var retArr = [];
str.replace(/(x_*)|(-)/g, function(match, p1, p2) {
  if (p1) { retArr.push({ on: true, length: p1.length }); }
  if (p2) { retArr.push({ on: false, length: 1 }); }
});

console.log(retArr);
```

This snippet generates an array of 3 objects in the desired format without using a `for` loop.
