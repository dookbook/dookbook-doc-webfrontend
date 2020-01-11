TOPICS: Element.getAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttribute()`

The **`getAttribute()`** method of the `Element` interface returns the value of a specified attribute
on the element. If the given attribute does not exist, the value returned will either be `null` or
`""` (the empty string); see Notes for details.

## Syntax

```javascript
let attribute = element.getAttribute(attributeName);
```

where

- `attribute` is a string containing the value of `attributeName`.
- `attributeName` is the name of the attribute whose value you want to get.

**Return value**: Returns a `ShadowRoot` object or `null`.

## Examples

```javascript
const div1 = document.getElementById('div1');
const align = div1.getAttribute('align');

alert(align); // Shows the value of align for the element with id="div1"
```

## Notes

When called on an HTML element in a DOM flagged as an HTML document, `getAttribute()` lower-cases its
argument before proceeding.

Essentially all web browsers (Firefox, Internet Explorer, recent versions of Opera, Safari,
Konqueror, and iCab, as a non-exhaustive list) return `null` when the specified attribute does not
exist on the specified element; this is what the current DOM specification draft specifies. The old
DOM 3 Core specification, on the other hand, says that the correct return value in this case is
actually the empty string, and some DOM implementations implement this behavior. The implementation
of `getAttribute()` in XUL (Gecko) actually follows the DOM 3 Core specification and returns an
empty string. Consequently, you should use `element.hasAttribute()` to check for an attribute's
existence prior to calling `getAttribute()` if it is possible that the requested attribute does not
exist on the specified element.
