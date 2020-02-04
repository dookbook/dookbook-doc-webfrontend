TOPICS: onanimationend

# `onanimationend`

事件处理程序。 当CSS动画到达其活动期的结束时发送此事件

## 语法

```javascript
var animEndHandler = target.onanimationend;

target.onanimationend = 事件处理函数
```

当`target`(HTML元素， `document` 或者 window)的CSS动画已经开始，`animationend`事件会触发同时*事件处理函数*会被调用。*事件处理函数*会接收到唯一的参数：
`AnimationEvent` 描述发生的事件。

## 示例

省略一些与此处讨论无关紧要的CSS，让我们看一下要设置动画的框的样式。首先是盒子本身。我们设置其大小，位置，颜色和布局。请注意，动画没有任何内容。那是因为我们不希望盒子立即开始动画。稍后我们将添加动画样式以开始对盒进行动画处理。

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
}
```

接下来描述动画序列。首先，`"slideAnimation"`类使用`"slideBox"`关键帧集建立动画，该动画将使框一次移动五秒钟。接下来定义关键帧。它们描述了一个动画，该动画使框从容器的左上角移到右下角。

```css
.slideAnimation {
  animation: 5s ease-in-out 0s 1 slideBox;
}

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

由于CSS描述了动画，但没有将动画连接到盒子，因此我们需要一些JavaScript代码。我们将尽快解决。

JavaScript内容

在获得动画代码之前，我们定义了一个函数，该函数将信息记录到用户屏幕上的框中。我们将使用它来显示有关收到的事件的信息。请注意，使用`AnimationEvent.animationName`和`AnimationEvent.elapsedTime`获取有关发生的事件的信息。

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

然后，我们为`animationstart`和`animationend`事件设置事件处理程序：

```javascript
let box = document.getElementById("box");

box.onanimationstart = function(event) {
  log("Animation started", event);
}

box.onanimationend = function(event) {
  log("Animation stopped", event);
};
```

最后，我们为单击运行动画的按钮设置了一个处理程序：

```javascript
document.getElementById("play").addEventListener("click", function(event) {
  document.getElementById("box").className = "slideAnimation";
  event.target.style.display = "none";
}, false);
```

这会将我们要设置动画的框的类设置为包含动画描述的类，然后隐藏“播放”按钮，因为此示例将只运行一次动画。 有关为什么以及如何支持多次运行动画的信息，请参阅CSS Animations技巧中的再次运行动画。
