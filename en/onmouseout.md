TOPICS: onmouseout
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onmouseout`

The **`onmouseout`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes mouseout events.

The `mouseout` event fires when the mouse leaves an element. For example, when the mouse moves off
of an image in the web page, the `mouseout` event is raised for that image element.

## Syntax

```javascript
element.onmouseout = function;
```

## Example

This example adds an `onmouseout` and an `onmouseover` event to a paragraph. Try moving your mouse
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
