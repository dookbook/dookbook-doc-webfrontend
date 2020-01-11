TOPICS: Element.removeAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.removeAttribute()`

The Element method **`removeAttribute()`** removes the attribute with the specified name from the element.

## Syntax

```javascript
element.removeAttribute(attrName);
```

| parameter | Description |
| :-- | :-- |
| `attrName` | A `DOMString` specifying the name of the attribute to remove from the element. If the specified attribute does not exist, `removeAttribute()` returns without generating an error.|

**Return value**: `undefined`.

!!! warn "Note"
    Since `removeAttribute()` doesn't return a value, you can't chain multiple calls together to
    remove multiple attributes at once.

## Usage notes

You should use `removeAttribute()` instead of setting the attribute value to null either directly or
using `setAttribute()`. Many attributes will not behave as expected if you set them to null.

## Examples

```javascript
// Given: <div id="div1" align="left" width="200px">
document.getElementById("div1").removeAttribute("align");
// Now: <div id="div1" width="200px">
```
