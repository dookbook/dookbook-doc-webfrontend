TOPICS: onscroll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onscroll`

元素的 **`scroll`** 事件处理函数。

## 语法

```javascript
element.onscroll = functionReference
```

- `functionReference` 是一个函数的引用。当该元素滚动时，会执行该函数。

!!! warn "注意"
    不要将 `onscroll` 与 `onwheel` 混淆。`onwheel`是鼠标滚轮旋转, 而 `onscroll` 处理的是对象内部内容区的滚动事件。

## 示例

```html
<!DOCTYPE html>
<html lang="en">
  <head>
  <meta charset="UTF-8" />
  <style>
  #container {
    position: absolute;
    height: auto;
    top: 0;
    bottom: 0;
    width: auto;
    left: 0;
    right: 0;
    overflow: auto;
  }

  #foo {
    height:1000px;
    width:1000px;
    background-color: #777;
    display: block;
  }

  </style>
  </head>
  <body>
    <div id="container">
      <div id="foo"></div>
    </div>

    <script type="text/javascript">
      document.getElementById('container').onscroll = function() {
        console.log("scrolling");
      };
    </script>
  </body>
</html>
```

此示例监视`<textarea>`上的滚动，并相应记录元素的垂直滚动位置。

```html
<textarea>1 2 3 4 5 6 7 8 9</textarea>
<p id="log"></p>
```

```css
textarea {
  width: 4rem;
  height: 8rem;
  font-size: 3rem;
}
```

```javascript
const textarea = document.querySelector('textarea');
const log = document.getElementById('log');

textarea.onscroll = logScroll;

function logScroll(e) {
  log.textContent = `Scroll position: ${e.target.scrollTop}`;
}
```
