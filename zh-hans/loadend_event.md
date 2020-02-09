TOPICS: onloadend
        loadend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `loadend` 事件

**`onloadend`** 属性表示当代码被调用时优先级提高，资源的加载事件触发时调用处理函数。

## 语法

```javascript
img.onloadend = funcRef;
```

`funcRef` 是在资源的 `loadend` 事件触发时要调用的处理函数。

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
