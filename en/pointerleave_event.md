TOPICS: onpointerleave
        pointerleave
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerleave` Event

The global event handler for the **`pointerleave`** event, which is delivered to a `Node` when the
pointer (mouse cursor, fingertip, etc.) exits its hit test area (for example, if the cursor exits an
[`Element`](/en/webfrontend/Element) or `Window`'s content area). This event is part of the Pointer
Events API.

## Syntax

```javascript
EventTarget.onpointerleave = leaveHandler;

var leaveHandler = EventTarget.onpointerleave;
```

**`leaveHandler`** The `EventListener` which will be invoked to handle `pointerleave` events
sent to the target.

## Example

This example shows two ways to use `onpointerleave` to set an element's `pointerleave` event handler.

```html
<html>
<script>
function leaveHandler(ev) {
 // Process the pointerleave event
}
function init() {
 var el=document.getElementById("target1");
 el.onpointerleave = leaveHandler;
}
</script>
<body onload="init();">
<div id="target1"> Touch me ... </div>
<div id="target2" onpointerleave="leaveHandler(event)"> Touch me ... </div>
</body>
</html>
```
