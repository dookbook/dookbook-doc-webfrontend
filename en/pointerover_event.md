TOPICS: onpointerover
        pointerover
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerover` Event

The **`onpointerover`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
**`pointerover`** events.

## Syntax

```javascript
targetElement.onpointerover = overHandler;

var overHandler = targetElement.onpointerover;
```

**`overHandler`** The `pointerover` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointerover` to set an element's `pointerover` event handler.

```html
<html>
<script>
function overHandler(ev) {
  // Process the pointerover event
}
function init() {
  let el=document.getElementById('target1');
  el.onpointerover = overHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerover="overHandler(event)"> Touch me ... </div>
</body>
</html>
```
