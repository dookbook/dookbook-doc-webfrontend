TOPICS: onmouseleave
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onmouseleave`

`GlobalEventHandlers` mixin 中的 **`onmouseleave`** 属性是用于处理鼠标移出（`mouseleave`）事件的事件管理器（`EventHandler`）。

`mouseleave`事件在定点设备(通常来说指的是鼠标) 移出某个元素时触发。

## 语法

```javascript
element.onmouseleave = handlerFunction;
var handlerFunction = element.onmouseleave;
```

`handlerFunction` 可以是 `null` ，也可以是一个用以指示如何处理该事件的 JavaScript 函数 。

## 示例

```html
<img onmouseenter="bigImg(this)" onmouseleave="normalImg(this)" border="0" src="smiley.gif" alt="Smiley" width="32" height="32">
<p>
bigImg() 函数在用户将鼠标指针移动到该图像时触发。</p>
<p>
normalImg() 函数在用户将鼠标指针移出图像时触发。</p>
<script>
function bigImg(x) {
  x.style.height = "64px";
  x.style.width = "64px";
}
function normalImg(x) {
  x.style.height = "32px";
  x.style.width = "32px";
}
</script>
```
