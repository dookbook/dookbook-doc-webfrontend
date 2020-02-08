TOPICS: ongotpointercapture
        gotpointercapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `gotpointercapture` Event

The **`ongotpointercapture`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes `gotpointercapture` events.

## Syntax

```javascript
target.ongotpointercapture = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a
`PointerEvent` object as its sole argument.

## Example

```javascript
function overHandler(event) {
  // Determine the target event's gotpointercapture handler
  let gotCaptureHandler = event.target.ongotpointercapture;
}

function init() {
  let el = document.getElementById('target');
  el.ongotpointercapture = overHandler;
}
```
