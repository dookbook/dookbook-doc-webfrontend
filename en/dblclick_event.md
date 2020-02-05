TOPICS: ondblclick
        dblclick
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `dblclick` Event

The **`ondblclick`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`dblclick` events on the given element.

The `dblclick` event is raised when the user double clicks an element. It fires after two `click` events.

## Syntax

```javascript
element.ondblclick = function;
```

`functionRef` is a function name or a function expression. The function receives a `MouseEvent`
object as its sole argument. Within the function, `this` will be the element upon which the event
was triggered.

Only one `ondblclick` handler can be assigned to an object at a time. You may prefer to use the
`EventTarget.addEventListener()` method instead, since it's more flexible.

## Example

This example logs the position of double clicks.

```html
<p>Double click anywhere in this example.</p>
<p id="log"></p>
```

```javascript
let log = document.getElementById('log');

document.ondblclick = logDoubleClick;

function logDoubleClick(e) {
  log.textContent = `Position: (${e.clientX}, ${e.clientY})`;
}
```
