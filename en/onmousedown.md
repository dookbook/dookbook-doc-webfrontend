TOPICS: onmousedown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onmousedown`

The **`onmousedown`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes `mousedown` events.

The `mousedown` event fires when the user depresses the mouse button.

!!! warn "Note"
    The opposite of `onmousedown` is `onmouseup`.

## Syntax

```javascript
target.onmousedown = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `MouseEvent`
object as its sole argument.

## Examples

This example reveals part of an image when you press and hold a mouse button. It uses the
`onmousedown`, `onmouseup`, and `onmousemove` event handlers.

```html
<div class="container">
  <div class="view" hidden></div>
  <img src="https://interactive-examples.mdn.mozilla.net/media/examples/gecko-320-213.jpg">
</div>
```

```css
.container {
  width: 320px;
  height: 213px;
  background: black;
}

.view {
  position: absolute;
  width: 100px;
  height: 100px;
  background: white;
  border-radius: 50%;
}

img {
  mix-blend-mode: darken;
}
```

```javascript
function showView(event) {
  view.removeAttribute('hidden');
  view.style.left = event.clientX - 50 + 'px';
  view.style.top = event.clientY - 50 + 'px';
  event.preventDefault();
}

function moveView(event) {
  view.style.left = event.clientX - 50 + 'px';
  view.style.top = event.clientY - 50 + 'px';
}

function hideView(event) {
  view.setAttribute('hidden', '');
}

const container = document.querySelector('.container');
const view = document.querySelector('.view');

container.onmousedown = showView;
container.onmousemove = moveView;
document.onmouseup = hideView;
```
