TOPICS: onkeyup
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onkeyup`

The **`onkeyup`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`keyup` events.

The `keyup` event fires when the user releases a key that was previously pressed.

## Syntax

```javascript
target.onkeyup = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `KeyboardEvent`
object as its sole argument.

## Example

This example logs the `KeyboardEvent.code` value whenever you release a key inside the `<input>` element.

```html
<input>
<p id="log"></p>
```

```javascript
const input = document.querySelector('input');
const log = document.getElementById('log');

input.onkeyup = logKey;

function logKey(e) {
  log.textContent += ` ${e.code}`;
}
```
