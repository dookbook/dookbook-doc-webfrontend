TOPICS: onmouseover
        mouseover
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mouseover` Event

The **`onmouseover`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes `mouseover` events.

The `mouseover` event fires when the user moves the mouse over a particular element.

## Syntax

```javascript
element.onmouseover = function;
```

## Example

This example adds an `onmouseover` and an `onmouseout` event to a paragraph. Try moving your mouse
over and out of the element.

```html
<p>Test your mouse on me!</p>
```

```javascript
const p = document.querySelector('p');
p.onmouseover = logMouseOver;
p.onmouseout = logMouseOut;

function logMouseOver() {
  p.innerHTML = 'MOUSE OVER detected';
}

function logMouseOut() {
  p.innerHTML = 'MOUSE OUT detected';
}
```
