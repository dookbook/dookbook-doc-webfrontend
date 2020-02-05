TOPICS: oninput
        input
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `input` Event

The `oninput` property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes `input`
events on the `<input>`, `<select>`, and `<textarea>` elements. It also handles these events on
elements where `contenteditable` or `designMode` are turned on.

!!! warn "Note"
    Unlike `oninput`, the `onchange` event handler is not necessarily called for each alteration
    to an element's `value`.

## Syntax

```html
target.oninput = functionRef;
```

`functionRef` is a function name or a function expression. The function receives an `InputEvent`
object as its sole argument.。

## Example

This example logs the number of characters in an `<input>` element, every time you modify its contents.

```html
<input type="text" placeholder="Type something here to see its length." size="50">
<p id="log"></p>
```

```javascript
let input = document.querySelector('input');
let log = document.getElementById('log');

input.oninput = handleInput;

function handleInput(e) {
  log.textContent = `The field's value is
      ${e.target.value.length} character(s) long.`;
}
```
