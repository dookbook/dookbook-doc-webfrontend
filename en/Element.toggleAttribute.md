TOPICS: Element.toggleAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.toggleAttribute()`

The **`toggleAttribute()`** method of the Element interface toggles a Boolean attribute (removing
it if it is present and adding it if it is not present) on the given element.

## Syntax

```javascript
Element.toggleAttribute(name [, force]);
```

| parameter | Description |
| :-- | :-- |
| `name` | A DOMString specifying the name of the attribute to be toggled. The attribute name is automatically converted to all lower-case when `toggleAttribute()` is called on an HTML element in an HTML document.|
| `force` Optional | A `boolean` value to determine whether the attribute should be added or removed, no matter whether the attribute is present or not at the moment.|

**Return value**: `true` if attribute name is eventually present, and `false` otherwise.

## Exceptions

|  |  |
| :-- | :-- |
| **`InvalidCharacterError`** | The specified attribute name contains one or more characters which are not valid in attribute names.|

## Examples

In the following example, `toggleAttribute()` is used to toggle the readonly attribute of a [`<input>`](/en/webfrontend/<input>).

```html
<input value="text">
<button>toggleAttribute("readonly")</button>
```

```javascript
var button = document.querySelector("button");
var input = document.querySelector("input");

button.addEventListener("click", function(){
  input.toggleAttribute("readonly");
});
```
