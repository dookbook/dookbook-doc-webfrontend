TOPICS: Element.hasPointerCapture

# `Element.hasPointerCapture()`

`Element` 接口的 **`hasPointerCapture()`** 方法设置在其上调用该元素的元素是否具有由给定指针ID标识的指针的指针捕获。

## 语法

```javascript
targetElement.hasPointerCapture(pointerId);
```

| 参数 | 说明 |
| :-- | :-- |
| `pointerId` | `PointerEvent`对象的`pointerId`。|

**Return value**: 一个布尔值—如果元素确实具有指针捕获，则为`true`；否则为`false`。

## 示例

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
