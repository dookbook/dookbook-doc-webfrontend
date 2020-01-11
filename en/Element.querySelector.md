TOPICS: Element.querySelector
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.querySelector()`

The **`querySelector()`** method of the `Element` interface returns the first element that is a
descendant of the element on which it is invoked that matches the specified group of selectors.

## Syntax

```javascript
element = baseElement.querySelector(selectors);
```

| parameter | Description |
| :-- | :-- |
| `selectors` | A group of selectors to match the descendant elements of the `Element` `baseElement` against; this must be valid CSS syntax, or a `SyntaxError` exception will occur. The first element found which matches this group of selectors is returned. |

## Return value

The first descendant element of `baseElement` which matches the specified group of `selectors`.
The entire hierarchy of elements is considered when matching, including those outside the set of
elements including `baseElement` and its descendants; in other words, `selectors` is first applied
to the whole document, not the `baseElement`, to generate an initial list of potential elements.
The resulting elements are then examined to see if they are descendants of `baseElement`. The first
match of those remaining elements is returned by the `querySelector()` method.

If no matches are found, the returned value is `null`.

## Exceptions

| parameter | Description |
| :-- | :-- |
| `SyntaxError` | The specified `selectors` are invalid

## Examples

### Find a specific element with specific values of an attribute

In this first example, the first `<style>` element which either has no type or has type `"text/css"`
in the HTML document body is returned:

```javascript
var el = document.body.querySelector("style[type='text/css'], style:not([type])");
```

### The entire hierarchy counts

This example demonstrates that the hierarchy of the entire document is considered when applying
`selectors`, so that levels outside the specified `baseElement` are still considered when locating matches.

```html
<div>
  <h5>Original content</h5>
  <p>
    inside paragraph
    <span>inside span</span>
    inside paragraph
  </p>
</div>
<div>
  <h5>Output</h5>
  <div id="output"></div>
</div>
```

```javascript
var baseElement = document.querySelector("p");
document.getElementById("output").innerHTML =
  (baseElement.querySelector("div span").innerHTML);
```
