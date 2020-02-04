TOPICS: onchange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onchange`

**`onchange`** 可以用来获取或设置当前元素的`change`事件的事件处理函数.

## 语法

```javascript
element.onchange = 事件处理函数
```

## 示例

下面的伪代码演示了,在Mozilla中,`onchange`事件是如何触发的:

```javascript
  control.onfocus = focus;
  control.onblur = blur;
  function focus () {
      original_value = control.value;
  }

  function blur () {
      if (control.value != original_value)
        control.onchange();
  }
```

因此,如果你在你的`focus`或`blur`事件的处理函数里修改一个控件的值的话,你可能遇到一些关于`change`事件意想不到的现象.另外, `change`事件是在`blur`事件发生之后才触发的.
这一点和IE不同.
