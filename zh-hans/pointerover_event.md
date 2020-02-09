TOPICS: onpointerover
        pointerover

# `pointerover` 事件

`GlobalEventHandlers` 混合的 **`onpointerover`** 属性是一个处理指针转换事件的`EventHandler`。

## 语法

```javascript
targetElement.onpointerover = overHandler;

var overHandler = targetElement.onpointerover;
```

**`overHandler`** 元素 `targetElement` 的指针事件处理程序。

## 示例

此示例显示了两种使用`onpointerover`设置元素的`pointerover`事件处理程序的方法。

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
