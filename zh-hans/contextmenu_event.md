TOPICS: oncontextmenu
        contextmenu
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `contextmenu` 事件

获取或设置当前窗口 **`contextmenu`** 事件的事件处理函数。除非默认行为已经阻止了(看下面的例子是如何阻止的)，否则右键菜单会被激活。注意此事件会发生在没有阻止右键事件的情况下而且这不取决于此元素是否拥有了`"contextmenu"`属性.

## 语法

```javascript
window.oncontextmenu = funcRef;
//funcRef是个函数引用
```

## 示例

这个例子会取消页面右键的功能：

```javascript
window.oncontextmenu = function () {
   return false;
}
//该窗口禁止使用右键
```
