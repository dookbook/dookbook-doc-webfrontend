TOPICS: onpointerenter
        pointerenter
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerenter` Event

The **`onpointerenter`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes **`pointerenter`** events.

## Syntax

```javascript
targetElement.onpointerenter = enterHandler;

var enterHandler = targetElement.onpointerenter;
```

**`enterHandler`** The `pointerenter` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointerenter` to set an element's `pointerenter` event handler.

```html
<html>
<script>
function enterHandler(ev) {
  // Process the pointerenter event
}
function init() {
  let el = document.getElementById('target1');
  el.onpointerenter = enterHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerenter="enterHandler(event)"> Touch me ... </div>
</body>
</html>
```
