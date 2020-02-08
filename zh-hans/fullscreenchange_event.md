TOPICS: onfullscreenchange
        fullscreenchange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `fullscreenchange` 事件

**`Document.onfullscreenchange`** 属性是 `fullscreenchange` 事件的处理器，这个事件在当前文档进入或者退出全屏的时候触发。

## 语法

```javascript
targetDocument.onfullscreenchange = fullscreenChangeHandler;
```

## 示例

```javascript
document.onfullscreenchange = function ( event ) {
  console.log("FULL SCREEN CHANGE")
};
document.documentElement.onclick = function () {
  // requestFullscreen() 方法必须在一个事件处理器的方法体里执行，否则将会失败
  document.documentElement.requestFullscreen();
}
```
