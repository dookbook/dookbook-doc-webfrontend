TOPICS: onpointermove
        pointermove
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointermove` Event

The **`onpointermove`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes **`pointermove`** events.

## Syntax

```javascript
targetElement.onpointermove = moveHandler;

var moveHandler = targetElement.onpointermove;
```

**`moveHandler`** The `pointermove` event handler for element `targetElement`.

## Example

This example shows two ways to use `onpointermove` to set an element's `pointermove` event handler.

```html
<html>
<script>
function moveHandler(ev) {
  // Process the pointermove event
}
function init() {
  let el=document.getElementById('target1');
  el.onpointermove = moveHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointermove="moveHandler(event)"> Touch me ... </div>
</body>
</html>
```
