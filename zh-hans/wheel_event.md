TOPICS: onwheel
        wheel

# `wheel` 事件

`GlobalEventHandlers` mixin的 **`onwheel`** 属性是一个处理车轮事件的`EventHandler`。

当用户旋转鼠标（或其他定点设备）滚轮时，将触发滚轮事件。

!!! warn "注意"
    不要将`onwheel`与`onscroll`混淆：`onwheel`处理一般的车轮旋转，而`onscroll`处理对象内容的滚动。

## 语法

```javascript
target.onwheel = functionRef;
```

`functionRef` 是函数名称或函数表达式。 该函数接收`WheelEvent`对象作为其唯一参数。

## 示例

本示例说明如何使用鼠标（或其他定点设备）滚轮缩放元素。

```html
<div>Scale me with your mouse wheel.</div>
```

```css
body {
  min-height: 100vh;
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

div {
  width: 80px;
  height: 80px;
  background: #cdf;
  padding: 5px;
  transition: transform .3s;
}
```

```javascript
function zoom(event) {
  event.preventDefault();

  if (event.deltaY < 0) {
    // Zoom in
    scale *= event.deltaY * -2;
  }
  else {
    // Zoom out
    scale /= event.deltaY * 2;
  }

  // Restrict scale
  scale = Math.min(Math.max(.125, scale), 4);

  // Apply scale transform
  el.style.transform = `scale(${scale})`;
}

let scale = 1;
const el = document.querySelector('div');
document.onwheel = zoom;
```
