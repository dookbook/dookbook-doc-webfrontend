TOPICS: onwheel
        wheel
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `wheel` Event

The **`onwheel`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
**`wheel`** events.

The **`wheel`** event fires when the user rotates the mouse (or other pointing device) `wheel`.

!!! warn "Note"
    Don't confuse `onwheel` with `onscroll`: `onwheel` handles general wheel rotation, while `onscroll`
    handles scrolling of an object's content.

## Syntax

```javascript
target.onwheel = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `WheelEvent`
object as its sole argument.

## Example

This example shows how to scale an element using the mouse (or other pointing device) wheel.

```html
<div>Scale me with your mouse wheel.</div>
```

```css
body {
  min-height: 100vh;
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

div {
  width: 80px;
  height: 80px;
  background: #cdf;
  padding: 5px;
  transition: transform .3s;
}
```

```javascript
function zoom(event) {
  event.preventDefault();

  if (event.deltaY < 0) {
    // Zoom in
    scale *= event.deltaY * -2;
  }
  else {
    // Zoom out
    scale /= event.deltaY * 2;
  }

  // Restrict scale
  scale = Math.min(Math.max(.125, scale), 4);

  // Apply scale transform
  el.style.transform = `scale(${scale})`;
}

let scale = 1;
const el = document.querySelector('div');
document.onwheel = zoom;
```
