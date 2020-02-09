TOPICS: ontransitionend
        transitionend

# `transitionend` 事件

`GlobalEventHandlers` 混合的 **`ontransitionend`** 属性是一个`EventHandler`，用于处理 **`transitionend`** 事件。

当CSS转换完成时，将发送 **`transitionend`** 事件。

!!! warn ""
    如果在转换完成执行之前将转换从其目标节点中删除，则不会生成`transitionend`事件。发生这种情况的一种方法是通过更改应用于目标的过渡属性属性的值。另一个是将`display`属性设置为`"none"`。

## 语法

```javascript
var transitionEndHandler = target.ontransitionend;

target.ontransitionend = Function
```

当`Transitionend`事件发生时要调用的函数，指示在目标上完成CSS转换，其中目标对象是HTML元素（`HTMLElement`），文档（`Document`）或窗口（`Window`）。该函数接收单个参数作为输入：一个描述所发生事件的`TransitionEvent`对象；事件的`TransitionEvent.elapsedTime`属性的值应与`transition-duration`的值相同。

!!! warn ""
   `elapsedTime`不包括过渡效果开始之前的时间；这意味着`transition-delay`的值不会影响`elapsedTime`的值，`elapsedTime`的值为零，直到延迟时间段结束并且动画开始。

## 示例

在此示例中，我们使用`transitionrun`和`transitionend`事件来检测过渡的开始和结束时间，以使文本在过渡期间发生更新。 这也可以用于触发动画或其他效果，以允许链接反应。

这只是创建一个[`<div>`](/zh-hans/webfrontend/<div>)，我们将在下面的CSS中对其进行样式设置，以使其成为可调整大小并更改颜色等的框。

```html
<div class="box"></div>
```

下面的CSS为该框设置样式并应用过渡效果，该效果会改变该框的颜色和大小，并导致该框旋转，而鼠标光标悬停在其上方。

```css
.box {
  margin-left: 70px;
  margin-top: 30px;
  border-style: solid;
  border-width: 1px;
  display: block;
  width: 100px;
  height: 100px;
  background-color: #0000FF;
  color: #FFFFFF;
  padding: 20px;
  font: bold 1.6em "Helvetica", "Arial", sans-serif;
  transition: width 2s, height 2s, background-color 2s, transform 2s, color 2s;
}

.box:hover {
  background-color: #FFCCCC;
  color: #000000;
  width: 200px;
  height: 200px;
  transform: rotate(180deg);
}
```

接下来，我们需要建立事件处理程序，以在转换开始和结束时更改框的文本内容。

```javascript
let box = document.querySelector(".box");
box.ontransitionrun = function(event) {
  box.innerHTML = "Zooming...";
}
box.ontransitionend = function(event) {
  box.innerHTML = "Done!";
}
```
