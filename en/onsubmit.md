TOPICS: onsubmit
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onsubmit`

The `onsubmit` property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`submit` events.

The `submit` event fires when the user submits a form.

## Syntax

```javascript
target.onsubmit = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `FocusEvent` object
as its sole argument.

## Example

This example demonstrates `oninvalid` and `onsubmit` event handlers on a form.

```html
<form id="form">
  <p id="error" hidden>Please fill out all fields.</p>

  <label for="city">City</label>
  <input type="text" id="city" required>

  <button type="submit">Submit</button>
</form>
<p id="thanks" hidden>Your data has been received. Thanks!</p>
```

```javascript
const form = document.getElementById('form');
const error = document.getElementById('error');
const city = document.getElementById('city');
const thanks = document.getElementById('thanks');

city.oninvalid = invalid;
form.onsubmit = submit;

function invalid(event) {
  error.removeAttribute('hidden');
}

function submit(event) {
  form.setAttribute('hidden', '');
  thanks.removeAttribute('hidden');

  // For this example, don't actually submit the form
  event.preventDefault();
}
```
