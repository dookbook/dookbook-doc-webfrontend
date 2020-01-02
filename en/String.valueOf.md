TOPICS: String.valueOf
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.valueOf()`

The **`valueOf()`** method returns the primitive value of a [`String`](/en/webfrontend/String) object.

## Syntax

```javascript
str.valueOf()
```

**parameter**: No parameters

**Return value**: A string representing the primitive value of a given `String` object.

## Description

The `valueOf()` method of [`String`](/en/webfrontend/String) returns the primitive value of a
[`String`](/en/webfrontend/String) object as a string data type. This value is equivalent to [`String.toString()`](/en/webfrontend/String.toString).

This method is usually called internally by JavaScript and not explicitly in code.

## Examples

### Using `valueOf()`

```javascript
var x = new String('Hello world');
console.log(x.valueOf()); // Displays 'Hello world'
```
