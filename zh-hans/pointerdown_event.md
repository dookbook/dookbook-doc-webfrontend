TOPICS: onpointerdown
        pointerdown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerdown` 事件

`GlobalEventHandlers` 事件处理程序 **`onpointerdown`** 用于为 **`pointerdown`** 事件指定事件处理程序，该事件在最初按下指针设备时触发。此事件可以发送到`Window`、[`Document`](/zh-hans/webfrontend/Document)和[`Element`](/zh-hans/webfrontend/Element)对象。

由于用户使用鼠标或与鼠标兼容的设备进行的活动而生成时，此函数在功能上等效于`mousedown`事件。 如果没有通过调用`preventDefault()`来取消`pointerdown`事件，那么大多数用户代理将触发`mousedown`事件，这样不使用指针事件的站点就可以使用。

您也可以使用`addEventListener()`为`pointerdown`事件添加一个监听器。

## 语法

```javascript
target.onpointerdown = downHandler;

var downHandler = target.onpointerdown;
```

一个`Function`，用于处理目标[`Element`](/zh-hans/webfrontend/Element)、[`Document`](/zh-hans/webfrontend/Document)或`Window`的`pointerdown`事件。它接收描述指针下降事件的`PointerEvent`作为输入。

## 示例

这个例子演示了如何使用`onpointerdown`监视和处理`pointerdown`事件。当然，您也可以使用`addEventListener()`。

首先，让我们看一下处理`pointerdown`事件的JavaScript代码。

```javascript
var targetBox = document.getElementById("target");

targetBox.onpointerdown = handleDown;

function handleDown(evt) {
  var action;

  switch(evt.pointerType) {
    case "mouse":
      action = "clicking";
      break;
    case "pen":
      action = "tapping";
      break;
    case "touch":
      action = "touching";
      break;
    default:
      action = "interacting with";
      break;
  }

  targetBox.innerHTML = "<strong>Thanks for " + action + " me!</strong>";
  evt.preventDefault();
}
```

这仅使用`onpointerdown`来建立函数`handleHandDown()`作为指针向下事件的事件处理程序。

然后，`handleDown()`函数查看`pointerType`的值来确定使用哪种指针设备，然后使用该信息来自定义字符串以替换目标框的内容。

然后调用事件的`preventDefault()`方法以确保不触发`mousedown`事件，如果我们为这些事件提供了处理程序，则可能会导致事件被处理两次，以防缺少指针事件支持。

我们还有一个`pointerup`事件的处理程序：

```javascript
targetBox.onpointerup = handleUp;

function handleUp(evt) {
  targetBox.innerHTML = "Tap me, click me, or touch me!";
  evt.preventDefault();
}
```

该代码的工作是在用户与元素的交互结束之后（例如，当他们释放鼠标按钮或从屏幕上抬起手写笔或手指时），将原始文本仅恢复到目标框中。

另外，该事件的`preventDefault（）`方法被调用，以确保不会不必要地触发`mouseup`事件。

HTML非常简单：

```html
<div id="target">
  Tap me, click me, or touch me!
</div>
```

CSS只是设置目标的外观，完全不影响其功能。

```css
#target {
  width: 400px;
  height: 30px;
  text-align: center;
  font: 16px "Open Sans", "Helvetica", sans-serif;
  color: white;
  background-color: blue;
  border: 2px solid darkblue;
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}
```
