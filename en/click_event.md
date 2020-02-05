TOPICS: onclick
        click
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `click` Event

The **`onclick`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
`click` events on a given element.

The `click` event is raised when the user clicks on an element. It fires after the `mousedown` and
`mouseup` events, in that order.

## Syntax

```javascript
element.onclick = functionRef;
```

``functionRef`` is a function name or a function expression. The function receives a `MouseEvent`
object as its sole argument. Within the function, `this` will be the element upon which the event
was triggered.

Only one `onclick` handler can be assigned to an object at a time. You may prefer to use the `EventTarget.addEventListener()`
method instead, since it's more flexible.

## Detecting clicks

This example simply changes the color of an element when it's clicked upon.

```html
<div id="demo">Click here</div>
```

```javascript
document.getElementById('demo').onclick = function changeContent() {
  document.getElementById('demo').innerHTML = "Help me";
  document.getElementById('demo').style = "Color: red";
}
```

## Getting the coordinates of clicks

This example displays the coordinates at which the most recent mouse button click occurred.

```html
<p>Click anywhere in this example.</p>
<p id="log"></p>
```

```javascript
let log = document.getElementById('log');

document.onclick = inputChange;

function inputChange(e) {
  log.textContent = `Position: (${e.clientX}, ${e.clientY})`;
}
```
