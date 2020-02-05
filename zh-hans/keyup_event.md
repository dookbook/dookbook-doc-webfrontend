TOPICS: onkeyup
        keyup
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `keyup` 事件

**`onkeyup`** 属性用来获取或设置当前元素的`keyup`事件的事件处理函数.

## 语法

```javascript
element.onkeyup = event handling code
```

## 示例

```html
<input type="text" onKeyUp="keyWasPressed(event)">
<script>function keyWasPressed(evt){ alert(evt.keyCode) }</script>
```

## 备注

在当前元素上释放键盘按键时会触发`keyup`事件.
