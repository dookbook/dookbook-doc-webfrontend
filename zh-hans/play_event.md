TOPICS: onplay
        play

# `play` 事件

`GlobalEventHandlers` 混合的 **`onplay`** 属性是用于处理播放事件的`EventHandler`。

## 语法

```javascript
element.onplay = handlerFunction;
var handlerFunction = element.onplay;
```

`handlerFunction` 应该为 `null` 或指定事件处理程序的JavaScript函数。

## 示例

```html
<p>This example demonstrates how to assign an "onplay" event to a video element.</p>

<video controls onplay="alertPlay()">
  <source src="mov_bbb.mp4" type="video/mp4">
  <source src="mov_bbb.ogg" type="video/ogg">
  Your browser does not support HTML5 video.
</video>

<p>Video courtesy of <a href="http://www.bigbuckbunny.org/" target="_blank">Big Buck Bunny</a>.</p>

<script>
function alertPlay() {
  alert("The video has started to play.");
}
</script>
```
