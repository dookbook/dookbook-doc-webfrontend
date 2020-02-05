TOPICS: onmousedown
        mousedown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mousedown` 事件

**`onmousedown`** 属性用来获取或设置当前元素的`mousedown`事件的事件处理函数.

## 语法

```javascript
element.onmousedown= event handling code
```

在当前元素上鼠标按下瞬间会触发`mousedown`事件.

## 示例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onmousedown示例演示</title>
<script>
function myFunction(elmnt,clr){
  elmnt.style.color=clr;
}
</script>
</head>
<body>

<p onmousedown="myFunction(this,'red')" onmouseup="myFunction(this,'green')">
单击文本改变颜色。触发一个带参数函数,当鼠标按钮被按下,,当释放鼠标按钮，再一次触发其他参数函数
</p>

</body>
</html>
```
