TOPICS: onchange
        change
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `change` Event

The **`onchange`** property of the `GlobalEventHandlers` mixin is an `EventHandler` for processing
`change` events.

`change` events fire when the user commits a value change to a form control. This may be done, for
example, by clicking outside of the control or by using the !!!Tab!!! key to switch to a different control.

!!! warn "Note"
    Unlike `oninput`, the `onchange` event handler is not necessarily called for each alteration to
    an element's `value`.

## Syntax

```javascript
target.onchange = functionRef;
```

`functionRef` is a function name or a function expression. The function receives an `Event` object
as its sole argument.

## Example

This example logs the number of characters in an `<input>` element, every time you modify its
contents and then change focus away from it.

```html
<input type="text" placeholder="Type something here, then click outside of the field." size="50">
<p id="log"></p>
```

```javascript
let input = document.querySelector('input');
let log = document.getElementById('log');

input.onchange = handleChange;

function handleChange(e) {
  log.textContent = `The field's value is
      ${e.target.value.length} character(s) long.`;
}
```
