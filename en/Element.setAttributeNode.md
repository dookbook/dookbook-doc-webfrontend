TOPICS: Element.setAttributeNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.setAttributeNode()`

The **`setAttributeNode()`** method adds a new Attr node to the specified element.

## Syntax

```javascript
var replacedAttr = element.setAttributeNode(attribute);
```

- `attribute` is the `Attr` node to set on the element.
- `replacedAttr` is the replaced attribute node, if any, returned by this function.

## Examples

This example copies the `align` attribute from one element to another.

```html
<div id="one" align="left">one</div>
<div id="two">two</div>
```

```javascript
let d1 = document.getElementById('one');
let d2 = document.getElementById('two');
let a = d1.getAttributeNode('align');

d2.setAttributeNode(a.cloneNode(true));

// Returns: 'left'
alert(d2.attributes[1].value);
```

## Notes

If the attribute named already exists on the element, that attribute is replaced with the new one
and the replaced one is returned.

This method is seldom used, with `Element.setAttribute()` usually being used to change element's attributes.
