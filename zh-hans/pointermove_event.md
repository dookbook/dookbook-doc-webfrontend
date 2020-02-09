TOPICS: onpointermove
        pointermove

# `pointermove` 事件

`GlobalEventHandlers` mixin的 **`onpointermove`** 属性是一个处理指针移动事件的 `EventHandler` 。

## 语法

```javascript
targetElement.onpointermove = moveHandler;

var moveHandler = targetElement.onpointermove;
```

**`moveHandler`** 元素 `targetElement` 的 `pointermove` 事件处理程序。

## 示例

此示例显示了两种使用`onpointermove`设置元素的`pointermove`事件处理程序的方法。

```html
<html>
<script>
function moveHandler(ev) {
 // 此处添加事件处理语句
}
function init() {
 var el=document.getElementById("target1");
 el.onpointermove = moveHandler;
}
</script>
<body onload="init();">
<div id="target1"> Touch me ... </div>
<div id="target2" onpointermove="moveHandler(event)"> Touch me ... </div>
</body>
</html>
```
