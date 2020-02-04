TOPICS: onselect
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onselect`

**`onselect`** 用来获取或设置当前窗口的`select`事件的事件处理函数

## 语法

```javascript
window.onselect = funcRef;
```

- `funcRef` 是个函数引用

## 示例

```html
<html>
<head>
<title>onselect test</title>

<style type="text/css">
.text1 { border: 2px solid red; }
</style>

<script type="text/javascript">

window.onselect = selectText;

function selectText()
{
 alert("检测到select事件!");
}
</script>
</head>

<body>
<textarea class="text1" cols="30" rows="3">
用鼠标高亮选择一些文本,来触发select事件
</textarea>
</body>
</html>
```

## 备注

只有在文本框和文本域内选择文本才会触发`select`事件.。
