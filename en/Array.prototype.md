TOPICS: Array.prototype
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Array.prototype`

The `@@unscopable` symbol property contains property names that were not included in the ECMAScript
standard prior to the ES2015 version. These properties are excluded from `with` statement bindings.

## Syntax

```javascript
arr[Symbol.unscopables]
```

## Description

The default array properties that are excluded from `with` bindings are:

- [`copyWithin()`](/en/webfrontend/Array.copyWithin)
- [`entries()`](/en/webfrontend/Array.entries)
- [`fill()`](/en/webfrontend/Array.fill)
- [`find()`](/en/webfrontend/Array.find)
- [`findIndex()`](/en/webfrontend/Array.findIndex)
- [`includes()`](/en/webfrontend/Array.includes)
- [`keys()`](/en/webfrontend/Array.keys)
- [`values()`](/en/webfrontend/Array.values)

See [`Symbol.unscopables`](/en/webfrontend/Symbol.unscopables) for how to set `unscopables` for
your own objects.

Property attributes of **`Array.prototype[@@unscopables]`**

|  |  |
| :--- | :--- |
| `Writable` | `no` |
| `Enumerable` | `no` |
| `Configurable` | `yes` |

## Examples

The following code works fine in ES5 and below. However, in ECMAScript 2015 and later, the [`Array.keys()`](/en/webfrontend/Array.keys)
method was introduced. That means that inside with environments, "keys" would now be the method and
not the variable. This is where now the built-in `@@unscopables` `Array.prototype[@@unscopables]`
symbol property comes into play and prevents that some of the Array methods are being scoped into
the `with` statement.

```javascript
var keys = [];

with (Array.prototype) {
  keys.push('something');
}

Object.keys(Array.prototype[Symbol.unscopables]);
// ["copyWithin", "entries", "fill", "find", "findIndex",
//  "includes", "keys", "values"]
```
