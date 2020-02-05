TOPICS: onreset
        reset
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `reset` Event

The **`onreset`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`reset` events.

The `reset` event fires when the user clicks a reset button in a form (`<input type="reset">`).

## Syntax

```javascript
target.onreset = functionRef;
```

`functionRef` is a function name or a function expression. The function receives an `Event` object
as its sole argument.

## Example

This example logs the current `Event.timeStamp` whenever you reset the form.

```html
<form id="form">
  <label>Test field: <input type="text"></label>
  <br><br>
  <button type="reset">Reset form</button>
</form>
<p id="log"></p>
```

```javascript
function logReset(event) {
  log.textContent = `Form reset! Time stamp: ${event.timeStamp}`;
}

const form = document.getElementById('form');
const log = document.getElementById('log');
form.onreset = logReset;
```
