TOPICS: Element.hasAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasAttributeNS()`

**`hasAttributeNS`** returns a boolean value indicating whether the current element has the
specified attribute.

## Syntax

```javascript
result = element.hasAttributeNS(namespace,localName)
```

- `result` is the boolean value `true` or `false`.
- `namespace` is a string specifying the namespace of the attribute.
- `localName` is the name of the attribute.

## Examples

```javascript
/// Check that the attribute exists before you set a value
var d = document.getElementById("div1");
if (d.hasAttributeNS(
       "http://www.mozilla.org/ns/specialspace/",
       "special-align")) {
  d.setAttribute("align", "center");
}
```
