TOPICS: onloadstart
        loadstart

# `loadstart` 事件

`GlobalEventHandlers` mixin的 **`onloadstart`** 属性是一个 `EventHandler`，代表引发 **`loadstart`** 事件时（资源加载开始时）要调用的代码。）

## 语法

```javascript
img.onloadstart = funcRef;
```

`funcRef` 是在资源的`loadstart`事件触发时要调用的处理函数。

## 示例

```html
<img src="myImage.jpg">
```

```javascript
// 'loadstart' fires first, then 'load', then 'loadend'

image.addEventListener('load', function(e) {
  console.log('Image loaded');
});

image.addEventListener('loadstart', function(e) {
  console.log('Image load started');
});

image.addEventListener('loadend', function(e) {
  console.log('Image load finished');
});
```
