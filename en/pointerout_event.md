TOPICS: onpointerout
        pointerout
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerout` Event

The **`onpointerout`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
**`pointerout`** events.

## Syntax

```javascript
targetElement.onpointerout = outHandler;

var outHandler = targetElement.onpointerout;
```

**`outHandler`** The `pointerout` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointerout` to set an element's `pointerout` event handler

```html
<html>
<script>
function outHandler(ev) {
  // Process the pointerout event
}
function init() {
  let el=document.getElementById('target1');
  el.onpointerout = outHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerout="outHandler(event)"> Touch me ... </div>
</body>
</html>
```
