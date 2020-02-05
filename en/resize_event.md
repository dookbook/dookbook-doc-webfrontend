TOPICS: onresize
        resize
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `resize` Event

The `onresize` property of the `GlobalEventHandlers` interface is an `EventHandler` that processes
`resize` events.

The `resize` event fires after the window has been resized.

## Syntax

```javascript
window.onresize = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `FocusEvent`
object as its sole argument.

## Examples

```html
<p>Resize the browser window to fire the <code>resize</code> event.</p>
<p>Window height: <span id="height"></span></p>
<p>Window width: <span id="width"></span></p>
```

```javascript
const heightOutput = document.querySelector('#height');
const widthOutput = document.querySelector('#width');

function resize() {
  heightOutput.textContent = window.innerHeight;
  widthOutput.textContent = window.innerWidth;
}

window.onresize = resize;
```
