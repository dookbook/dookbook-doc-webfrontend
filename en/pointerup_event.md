TOPICS: onpointerup
        pointerup
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerup` Event

The **`onpointerup`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
**`pointerup`** events.

## Syntax

```javascript
targetElement.onpointerup = upHandler;

var upHandler = targetElement.onpointerup;
```

**`upHandler`** The `pointerup` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointerup` to set an element's `pointerup` event handler.

```html
<html>
<script>
function upHandler(ev) {
  // Process the pointerup event
}
function init() {
  let el = document.getElementById('target1');
  el.onpointerup = upHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerup="upHandler(event)"> Touch me ... </div>
</body>
</html>
```
