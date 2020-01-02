TOPICS: String.toString
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toString()`

The **`toString()`** method returns a string representing the specified object.

## Syntax

```javascript
str.toString()
```

**parameter**: No parameters

**Return value**: A string representing the calling object.

## Description

The [`String`](/en/webfrontend/String) object overrides the `toString()` method of the Object object;
it does not inherit [`Object.toString()`](/en/webfrontend/Object.toString). For [`String`](/en/webfrontend/String)
objects, the `toString()` method returns a string representation of the object and is the same as
the [`String.valueOf()`](/en/webfrontend/String.valueOf) method.

## Examples

### Using `toString()`

The following example displays the string value of a [`String`](/en/webfrontend/String) object:

```javascript
var x = new String('Hello world');

console.log(x.toString()); // logs 'Hello world'
```
