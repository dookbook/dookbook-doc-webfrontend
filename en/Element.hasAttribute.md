TOPICS: Element.hasAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasAttribute()`

The **`Element.hasAttribute()`** method returns a **Boolean** value indicating whether the specified
element has the specified attribute or not.

## Syntax

```javascript
var result = element.hasAttribute(name);
```

- `result` holds the return value `true` or `false`.
- `name` is a string representing the name of the attribute.

## Examples

```javascript
var foo = document.getElementById("foo");
if (foo.hasAttribute("bar")) {
    // do something
}
```

## Polyfill

```javascript
;(function(prototype) {
    prototype.hasAttribute = prototype.hasAttribute || function(name) {
        return !!(this.attributes[name] &&
                  this.attributes[name].specified);
    }
})(Element.prototype);
```
