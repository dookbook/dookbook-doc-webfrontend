TOPICS: onlostpointercapture
        lostpointercapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `lostpointercapture` Event

The **`onlostpointercapture`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes **`lostpointercapture`** events.

## Syntax

```javascript
target.onlostpointercapture = functionRef;
```

`functionRef` is a function name or a function expression. The function receives a `PointerEvent`
object as its sole argument.

## Example

```javascript
function overHandler(event) {
  // Determine the target event's lostpointercapture handler
  let lostCaptureHandler = event.target.onlostpointercapture;
}

function init() {
  let el = document.getElementById('target');
  el.onlostpointercapture = overHandler;
}
```
