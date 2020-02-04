TOPICS: onload
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onload`

`GlobalEventHandlers` mixin 的 `onload` 属性是一个事件处理程序用于处理`Window`, `XMLHttpRequest`, `<img>` 等元素的加载事件，当资源已加载时被触发。

## 语法

```javascript
window.onload = funcRef;
```

- 当 window `load` 事件触发时，`funcRef` 方法会被调用。

`funcRef` 是窗口加载事件触发时调用的处理函数。

## 示例

```javascript
window.onload = function() {
  init();
  doSomethingElse();
};
```

```html
<!doctype html>
<html>
  <head>
    <title>onload test</title>
    // ES5
    <script>
      function load() {
        console.log("load event detected!");
      }
      window.onload = load;
    </script>
    // ES2015(aka: ES6)
    <script>
      const load = () => {
        console.log("load event detected!");
      }
      window.onload = load;
    </script>
  </head>
  <body>
    <p>The load event fires when the document has finished loading!</p>
  </body>
</html>
```

## 注意

在文档装载完成后会触发 `load` 事件。此时，在文档中的所有对象都在DOM中，所有图片，脚本，链接以及子框都完成了装载。

同时也会有 Gecko-指定 DOM事件，如 `DOMContentLoaded` 和 `DOMFrameContentLoaded` (它们可以使用 `EventTarget.addEventListener()`
来处理 ) ， 这些事件在页面DOM构建起来后就会触发，而不会等到其他的资源都装载完成。
