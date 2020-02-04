TOPICS: onkeydown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onkeydown`

**`onkeydown`** 属性用来获取或设置当前元素的`keydown`事件的事件处理函数.

## 语法

```javascript
element.onkeydown = event handling code
```

## 备注

当用户按下键盘上的按键时会触发`keydown`事件

## 示例

```html
<p>当你在输入框内按下一个按键是函数被触发</p>
<input type="text" onkeydown="myFunction()">

<script>
function myFunction(){
  alert("你在输入栏内按下一个键");
}
</script>
```
