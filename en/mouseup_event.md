TOPICS: onmouseup
        mouseup
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mouseup` Event

The **`onmouseup`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
**`mouseup`** events.

The **`mouseup`** event fires when the user releases the mouse button.

!!! warn "Note"
    The opposite of `onmouseup` is `onmousedown`.

## Syntax

```javascript
target.onmouseup = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `MouseEvent`
object as its sole argument.

## Example

In this example, a piece of "toast" hides when you click down with the mouse, and reappears when
you release. It uses the `onmousedown` and `onmouseup` event handlers.

```html
<div class="container">
  <div class="toaster"></div>
  <div class="toast">Hello world!</div>
</div>
```

```css
.container {
  position: absolute;
  left: 50%;
  bottom: 20px;
  transform: translate(-50%);
}

.toaster {
  width: 160px;
  height: 110px;
  background: #bbb;
  border-radius: 10px 10px 0 0;
}

.toast {
  position: absolute;
  left: 50%;
  top: 50%;
  z-index: -1;
  width: 100px;
  height: 50px;
  padding: 10px;
  background: #ed9;
  border-radius: 10px 10px 0 0;
  transform: translate(-50%, -90px);
  transition: transform .3s;
}

.depressed {
  transform: translate(-50%, -50%);
}
```

```javascript
function depress() {
  toast.classList.add('depressed');
}

function release() {
  toast.classList.remove('depressed');
}

const toaster = document.querySelector('.toaster');
const toast = document.querySelector('.toast');

toaster.onmousedown = depress;
document.onmouseup = release;
```
