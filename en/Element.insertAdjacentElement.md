TOPICS: Element.insertAdjacentElement
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.insertAdjacentElement()`

The **`insertAdjacentElement()`** method of the `Element` interface inserts a given element node
at a given position relative to the element it is invoked upon.

## Syntax

```javascript
targetElement.insertAdjacentElement(position, element);
```

| parameter | Description |
| :-- | :-- |
|`position` | A `DOMString` representing the position relative to the `targetElement`; must match (case-insensitively) one of the following strings:<br><br>1. `'beforebegin'`: Before the `targetElement` itself.<br>2. `'afterbegin'`: Just inside the `targetElement`, before its first child.<br>3. `'beforeend'`: Just inside the `targetElement`, after its last child.<br>4. `'afterend'`: After the `targetElement` itself.
| `element` | The element to be inserted into the tree.

**Return value**: The element that was inserted, or `null`, if the insertion failed.

## Exceptions

| `Exception` | `Explanation` |
| `SyntaxError` | The `position` specified is not a recognised value. |
| `TypeError` | The `element` specified is not a valid element. |

## Visualization of position names

```html
<!-- beforebegin -->
<p>
  <!-- afterbegin -->
  foo
  <!-- beforeend -->
</p>
<!-- afterend -->
```

!!! warn "Note"
    The `beforebegin` and `afterend` positions work only if the node is in a tree and has an
    element parent.

## Examples

```javascript
beforeBtn.addEventListener('click', function() {
  var tempDiv = document.createElement('div');
  tempDiv.style.backgroundColor = randomColor();
  if (activeElem) {
    activeElem.insertAdjacentElement('beforebegin',tempDiv);
  }
  setListener(tempDiv);
});

afterBtn.addEventListener('click', function() {
  var tempDiv = document.createElement('div');
  tempDiv.style.backgroundColor = randomColor();
  if (activeElem) {
    activeElem.insertAdjacentElement('afterend',tempDiv);
  }
  setListener(tempDiv);
});
```
