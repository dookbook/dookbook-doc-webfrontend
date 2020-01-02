TOPICS: String.search
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.search()`

The **`search()`** method executes a search for a match between a regular expression and this
[`String`](/en/webfrontend/String) object.

## Syntax

```javascript
str.search(regexp)
```

| parameter | Description |
| :-- | :-- |
| `regexp` | A regular expression object.
If a non-RegExp object `regexp` is passed, it is implicitly converted to a `RegExp` with `new RegExp(regexp)`. |

**Return value**: The index of the first match between the regular expression and the given string,
or `-1` if no match was found.

## Description

When you want to know whether a pattern is found, and also know its index within a string, use
`search()`. (If you only want to know if it exists, use the similar `test()` method on the `RegExp`
prototype, which returns a boolean.)

For more information (but slower execution) use [`match()`](/en/webfrontend/String.match) (similar
to the regular expression `exec()` method).

## Examples

### Using `search()`

The following example searches a string with two different regex objects to show a successful
search (positive value) vs. an unsuccessful search (`-1`)

```javascript
let str = "hey JudE"
let re = /[A-Z]/g
let re2 = /[.]/g
console.log(str.search(re))   // returns 4, which is the index of the first capital letter "J"
console.log(str.search(re2))  // returns -1 cannot find '.' dot punctuation
```
