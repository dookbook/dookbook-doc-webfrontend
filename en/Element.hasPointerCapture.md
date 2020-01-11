TOPICS: Element.hasPointerCapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasPointerCapture()`

The **`hasPointerCapture()`** method of the `Element` interface sets whether the element on which
it is invoked has pointer capture for the pointer identified by the given pointer ID.

## Syntax

```javascript
targetElement.hasPointerCapture(pointerId);
```

| parameter | Description |
| :-- | :-- |
| `pointerId` | The `pointerId` of a `PointerEvent` object.

**Return value**: A `Boolean` value — `true` if the element does have pointer capture, `false` if
it doesn't.

## Examples

```html
<html>
  <script>
    function downHandler(ev) {
      const el = document.getElementById("target");
      // Element 'target' will receive/capture further events
      el.setPointerCapture(ev.pointerId);

      /* ... */

      // Check whether element still has pointer capture
      let pointerCap = el.hasPointerCapture(ev.pointerId);
      if(pointerCap) {
        // We've still got pointer capture
      } else {
        // oops, we've lost pointer capture!
      }
    }

    function init() {
      const el = document.getElementById("target");
      el.onpointerdown = downHandler;
    }
  </script>
  <body onload="init();">
    <div id="target">Touch this element with a pointer.</div>
  </body>
</html>
```
