TOPICS: Element.insertAdjacentText
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.insertAdjacentText()`

The **`insertAdjacentText()`** method of the `Element` interface inserts a given text node at a
given position relative to the element it is invoked upon.

## Syntax

```javascript
element.insertAdjacentText(position, element);
```

| parameter | Description |
| :-- | :-- |
| `position` | A `DOMString` representing the position relative to the `element`; must be one of the following strings:<br><br>1. `'beforebegin'`: Before the `element` itself.<br>2. `'afterbegin'`: Just inside the `element`, before its first child.<br>3. `'beforeend'`: Just inside the `element`, after its last child.<br>4. `'afterend'`: After the `element` itself. |
| `element` | A `DOMString` representing the text to be inserted into the tree. |

**Return value**: Void.

## Exceptions

| Exception | Explanation |
| `SyntaxError` | The `position` specified is not a recognised value.

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
  para.insertAdjacentText('afterbegin',textInput.value);
});

afterBtn.addEventListener('click', function() {
  para.insertAdjacentText('beforeend',textInput.value);
});
```
