TOPICS: onfullscreenerror
        fullscreenerror
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `fullscreenerror` 事件

**`Document.onfullscreenerror`** 属性是一个事件处理器用于处理 `fullscreenchange` 事件,在当前文档不能进入全屏模式，即使它被请求时触发。

## 语法

```javascript
targetDocument.onfullscreenerror = fullscreenErrorHandler;
```

## 示例

```javascript
document.onfullscreenerror = function ( event ) {
  console.log("FULL SCREEN DENIED")
};

// requestFullscreen()将会失败，因为它在事件处理器之外
document.documentElement.requestFullscreen();
```
