TOPICS: Document.exitFullscreen
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.exitFullscreen()`

**`Document.exitFullscreen()`** 方法用于让当前文档退出全屏模式（原文表述不准确，详见备注）。调用这个方法会让文档回退到上一个调用`Element.requestFullscreen()`方法进入全屏模式之前的状态。

!!! warn "备注"
    如果一个元素A在请求进去全屏模式之前，已经存在其他元素处于全屏状态，当这个元素A退出全屏模式之后，之前的元素仍然处于全屏状态。浏览器内部维护了一个全屏元素栈用于实现这个目的。

## 语法

```javascript
document.exitFullscreen();
```

## 示例

```javascript
// 点击切换全屏模式
document.onclick = function (event) {
  if (document.fullscreenElement) {
    document.exitFullscreen()
  } else {
    document.documentElement.requestFullscreen()
  }
};
```
