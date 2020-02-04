TOPICS: onblur
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onblur`

The **`onblur`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
`blur` events. It's available on `Element`, `Document`, and `Window`.

The `blur` event is raised when an element loses focus.

!!! warn "Note"
    The opposite of `onblur` is `onfocus`.

## Syntax

```javascript
target.onblur = functionRef;
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
