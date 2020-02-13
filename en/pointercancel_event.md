TOPICS: onpointercancel
        pointercancel
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointercancel` Event

The **`onpointercancel`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
**`processes`** pointercancel events.

## Syntax

```javascript
targetElement.onpointercancel = cancelHandler;

var cancelHandler = targetElement.onpointercancel;
```

**`cancelHandler`** The `pointercancel` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointercancel` to handle an element's `pointercancel` events.

```html
<html>
<script>
function cancelHandler(ev) {
  // Process the pointercancel event
}
function init() {
  var el = document.getElementById('target1');
  el.onpointercancel = cancelHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointercancel="cancelHandler(event)"> Touch me ... </div>
</body>
</html>
```
