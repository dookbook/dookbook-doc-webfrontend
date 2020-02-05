TOPICS: onblur
        blur
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `blur` 事件

**`onblur`**属性用来获取或设置当前元素的`onBlur`事件的事件处理函数

## 语法

```javascript
element.onblur = function;
```

- `function` 是一个函数名, 没有括号`()`和任何参数,也可以是一个匿名函数,如下:

```javascript
element.onblur = function() { alert("检测到onblur事件!"); };
```

## 示例

```html
<html>
<head>
<title>onblur event example</title>
<script type="text/javascript">
  var elem = null;

  function initElement() {
    elem = document.getElementById("foo");
    // 注意:doEvent() 和 doEvent(param)都是不正确的.这里只能是函数名,不能是函数调用.
    elem.onblur = doEvent;
  };

  function doEvent() {
    elem.value = 'Bye-Bye';
    alert("检测到onblur事件!")
  }
</script>

<style type="text/css">
  #foo {
    border: solid blue 2px;
  }
</style>
</head>
<body onload="initElement()";>

<form>
  <input type="text" id="foo" value="Hello!" />
</form>

<p>点击input元素使其获得焦点,然后点击其他页面其他部位</p>

</body>
</html>
```

## 备注

当一个元素失去焦点时会触发`blur`事件.

在IE中,几乎所有类型的元素都可以触发`blur`事件,但在基于gecko的浏览器中,大部分元素都不能触发`blur`事件.
