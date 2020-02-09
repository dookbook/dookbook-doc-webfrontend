TOPICS: onmouseup
        mouseup
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mouseup` 事件

`GlobalEventHandlers` mixin的 **`onmouseup`** 属性是一个处理鼠标事件的`EventHandler`。

用户释放鼠标按钮时，将触发 **`mouseup`** 事件。

!!! warn "注意"
    `onmouseup`的反义词是`onmousedown`。

## 语法

```javascript
target.onmouseup = functionRef;
```

`functionRef` 是函数名称或函数表达式。 该函数接收`MouseEvent`对象作为其唯一参数。

## 示例

在此示例中，当您用鼠标单击时，一片“吐司”会隐藏，而在释放时会再次出现。它使用`onmousedown`和`onmouseup`事件处理程序。

```html
<div class="container">
  <div class="toaster"></div>
  <div class="toast">Hello world!</div>
</div>
```

```css
.container {
  position: absolute;
  left: 50%;
  bottom: 20px;
  transform: translate(-50%);
}

.toaster {
  width: 160px;
  height: 110px;
  background: #bbb;
  border-radius: 10px 10px 0 0;
}

.toast {
  position: absolute;
  left: 50%;
  top: 50%;
  z-index: -1;
  width: 100px;
  height: 50px;
  padding: 10px;
  background: #ed9;
  border-radius: 10px 10px 0 0;
  transform: translate(-50%, -90px);
  transition: transform .3s;
}

.depressed {
  transform: translate(-50%, -50%);
}
```

```javascript
function depress() {
  toast.classList.add('depressed');
}

function release() {
  toast.classList.remove('depressed');
}

const toaster = document.querySelector('.toaster');
const toast = document.querySelector('.toast');

toaster.onmousedown = depress;
document.onmouseup = release;
```
