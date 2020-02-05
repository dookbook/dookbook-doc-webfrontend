TOPICS: onkeydown
        keydown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `keydown` Event

The **`onkeydown`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`keydown` events.

The `keydown` event fires when the user presses a keyboard key.

## Syntax

```javascript
target.onkeydown = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `KeyboardEvent`
object as its sole argument.

## Example

This example logs the `KeyboardEvent.code` value whenever you press down a key inside the `<input>` element.

```html
<input>
<p id="log"></p>
```

```javascript
const input = document.querySelector('input');
const log = document.getElementById('log');

input.onkeydown = logKey;

function logKey(e) {
  log.textContent += ` ${e.code}`;
}
```
