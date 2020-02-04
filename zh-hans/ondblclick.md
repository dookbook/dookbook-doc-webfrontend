TOPICS: ondblclick
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ondblclick`

**`ondblclick`** 属性用来获取或设置当前元素的`dblclick`事件的事件处理函数.

## 语法

```javascript
element.ondblclick = function;
```

- `function` 是一个函数名,后面没有括号`()`,或者是一个匿名的函数表达式,比如

```javascript
element.ondblclick = function() { alert("触发了dblclick事件!"); };
```

## 示例

```html
<html>
<head>
<title>ondblclick示例演示</title>
<script type="text/javascript">
  function initElement() {
    var p = document.getElementById("foo");
    // 注意:这里写成showAlert()或者 showAlert(参数)是不对的.
    // 必须是一个函数名,而不是函数调用.
    p.ondblclick = showAlert;
  };

  function showAlert() {
    alert("检测到dblclick事件!")
  }
</script>

<style type="text/css">
#foo {
  border: solid blue 2px;
}
</style>
</head>
<body onload="initElement()";>
<span id="foo">这是一个元素</span>
<p>双击上面的元素会触发dblclick事件.</p>
</body>
</html>
```

## 备注

在当前元素上双击鼠标左键会触发`dblclick`事件.
