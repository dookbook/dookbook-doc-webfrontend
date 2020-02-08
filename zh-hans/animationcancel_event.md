TOPICS: onanimationcancel
        animationcancel

# `animationcancel` 事件

**`animationcancel`** 是一个事件处理操作,这个事件在CSS Animation属性意外中断时派发出来(换句话说，任何时候`animation`停止运行不会发出一个`animationend`
事件，比如，当`animation-name`改变以后，`animation` 就会被移除，或者动画节点隐藏—当前元素或者任何包含的节点隐藏)—使用CSS时

## 语法

```javascript
var animCancelHandler = target.onanimationcancel;

target.onanimationcancel = Function
```

当`animationcancel`事件发生时要调用的函数，指示CSS动画已在目标上开始，其中目标对象是HTML元素（`HTMLElement`），文档（`Document`）或窗口（`Window`）。该函数将单个参数作为输入接收：一个描述事件发生的`AnimationEvent`对象。

## 示例

```html
<div class="main">
  <div id="box">
    <div id="text" onanimationcancel="handleCancelEvent">Box</div>
  </div>
</div>

<div class="button" id="toggleBox">
  Hide the Box
</div>

<pre id="log"></pre>
```

省略一些与此处讨论无关紧要的CSS，让我们看一下要设置动画的框的样式。首先是盒子本身，其所有属性（包括动画）都已定义。我们继续在此处描述动画，因为动画旨在在页面加载后立即开始，而不是基于事件。

```css
#box {
  width: var(--boxwidth);
  height: var(--boxwidth);
  left: 0;
  top: 0;
  border: 1px solid #7788FF;
  margin: 0;
  position: relative;
  background-color: #2233FF;
  display: flex;
  justify-content: center;
  animation: 5s ease-in-out 0s infinite alternate both slideBox;
}
```

接下来描述动画的关键帧，绘制从内容框的左上角到右下角的路线。

```javascript
@keyframes slideBox {
  from {
    left:0;
    top:0;
  }
  to {
    left:calc(100% - var(--boxwidth));
    top:calc(100% - var(--boxwidth))
  }
}
```

由于动画被描述为无数次发生，每次交替方向，因此该框将在两个角之间来回滑动，直到停止或关闭页面为止。

在获得动画代码之前，我们定义了一个函数，该函数将信息记录到用户屏幕上的框中。 我们将使用它来显示有关收到的事件的信息。 请注意，使用`AnimationEvent.animationName和AnimationEvent.elapsedTime`获取有关发生的事件的信息。

```javascript
function log(msg, event) {
  let logBox = document.getElementById("log");

  logBox.innerHTML += msg;

  if (event) {
    logBox.innerHTML += " <code>"+ event.animationName +
        "</code> at time " + event.elapsedTime.toFixed(2) +
        " seconds.";
  }

  logBox.innerHTML += "\n";
};
```

然后，我们设置`handleCancelEvent()`函数，以响应`animationcancel`事件来调用该函数，如上面的HTML所示。 我们在这里所做的只是将信息记录到控制台，但是您可能会发现其他用例，例如开始一个新的动画或效果，或终止一些相关的操作。

```javascript
function handleCancelEvent(event) {
  log("Animation canceled", event);
};
```

然后，我们添加一种方法来处理`"flex"`和`"none"`之间的切换显示，并将其建立为“隐藏/显示”框按钮上的`click`事件的处理程序：

```javascript
function toggleBox() {
  if (box.style.display == "none") {
    box.style.display = "flex";
    document.getElementById("toggleBox").innerHTML = "Hide the box";
  } else {
    box.style.display = "none";
    document.getElementById("toggleBox").innerHTML = "Show the box";
  }
}
```

将框切换为`display：none`具有中止其动画的效果。 在支持`animationcancel`的浏览器中，将触发该事件并调用此处理程序。

目前，没有主流浏览器支持`animationcancel`。

如果您的浏览器支持`animationcancel`，则使用按钮隐藏该框将导致显示有关该事件的消息。
