TOPICS: onselect
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onselect`

The **`onselect`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`select` events.

The `select` event only fires after text inside an `<input type="text">` or `<textarea>` is selected.

## Syntax

```javascript
target.onselect = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `UIEvent` object
as its sole argument.

## Example

```html
<textarea>Try selecting some text in this element.</textarea>
<p id="log"></p>
```

```javascript
function logSelection(event) {
  const log = document.getElementById('log');
  const selection = event.target.value.substring(event.target.selectionStart, event.target.selectionEnd);
  log.textContent = `You selected: ${selection}`;
}

const textarea = document.querySelector('textarea');
textarea.onselect = logSelection;
```
