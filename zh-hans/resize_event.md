TOPICS: onresize
        resize
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `resize` 事件

**`onresize`** 属性可以用来获取或设置当前窗口的`resize`事件的事件处理函数

## 语法

```javascript
window.onresize = funcRef;
```

- `funcRef` 是一个函数引用

## 示例

在窗口大小改变之后,就会触发`resize`事件.

```javascript
window.onresize = doFunc;
```

```html
<html>
<head>

<title>onresize测试</title>

<script type="text/javascript">

window.onresize = resize;

function resize()
{
 alert("检测到resize事件!");
}
</script>
</head>

<body>
<p>改变浏览器窗口的大小来触发resize事件.</p>
</body>
</html>
```
