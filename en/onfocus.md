TOPICS: onfocus
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onfocus`

The **`onfocus`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`focus` events on the given element.

The `focus` event is raised when the user sets focus on an element.

For `onfocus` to fire on non-input elements, they must be given the `tabindex` attribute
(see Building keyboard accessibility back in for more details).

!!! warn "Note"
    The opposite of `onfocus` is `onblur`.

## Syntax

```javascript
target.onfocus = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `FocusEvent`
object as its sole argument.

## Example

This example uses `onblur` and `onfocus` to change the text within an `<input>` element.

```html
<input type="text" value="CLICK HERE">
```

```javascript
let input = document.querySelector('input');

input.onblur = inputBlur;
input.onfocus = inputFocus;

function inputBlur() {
  input.value = 'Focus has been lost';
}

function inputFocus() {
  input.value = 'Focus is here';
}
```
