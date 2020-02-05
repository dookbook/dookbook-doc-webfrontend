TOPICS: onmousemove
        mousemove
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mousemove` 事件

**`onmousemove`** 属性用来获取或设置当前元素的`mousemove`事件的事件处理函数.

## 语法

```javascript
element.onmousemove = event handling code
```

当用户在当前元素上移动鼠标时会触发`mousemove`事件.

## 示例

下面的例子演示了在显示"提示层"时`onmousemove`的用法.

```html
<!doctype html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Tooltip Example</title>
<script type="text/javascript">
var oTooltip = new (function() {
  var nOverX, nOverY, nLeftPos, nTopPos, oNode, bOff = true;
  this.follow = function (oMsEvnt1) {
    if (bOff) { return; }
    var nMoveX =  oMsEvnt1.clientX, nMoveY =  oMsEvnt1.clientY;
    nLeftPos += nMoveX - nOverX; nTopPos += nMoveY - nOverY;
    oNode.style.left = nLeftPos + "px";
    oNode.style.top = nTopPos + "px";
    nOverX = nMoveX; nOverY = nMoveY;
  };
  this.remove = function () {
    if (bOff) { return; }
    bOff = true; document.body.removeChild(oNode);
  };
  this.append = function (oMsEvnt2, sTxtContent) {
    oNode.innerHTML = sTxtContent;
    if (bOff) { document.body.appendChild(oNode); bOff = false; }
    var nScrollX = document.documentElement.scrollLeft || document.body.scrollLeft, nScrollY = document.documentElement.scrollTop || document.body.scrollTop, nWidth = oNode.offsetWidth, nHeight = oNode.offsetHeight;
    nOverX = oMsEvnt2.clientX; nOverY = oMsEvnt2.clientY;
    nLeftPos = document.body.offsetWidth - nOverX - nScrollX > nWidth ? nOverX + nScrollX + 10 : document.body.offsetWidth - nWidth + 16;
    nTopPos = nOverY - nHeight > 6 ? nOverY + nScrollY - nHeight - 7 : nOverY + nScrollY + 20;
    oNode.style.left = nLeftPos + "px";
    oNode.style.top = nTopPos + "px";
  };
  this.init = function() {
    oNode = document.createElement("div");
    oNode.className = "tooltip";
    oNode.style.position = "absolute";
  };
})();
</script>
<style type="text/css">
div.tooltip {
  padding: 6px;
  background: #ffffff;
  border: 1px #76808C solid;
  border-radius: 5px;
  -moz-border-radius: 5px;
  -webkit-border-radius: 5px;
  z-index: 9999;
}
</style>
</head>

<body onload="oTooltip.init();">
<p><a href="http://developer.mozilla.org/" onmouseover="oTooltip.append(event,'提示文字1');" onmousemove="oTooltip.follow(event);" onmouseout="oTooltip.remove();">将你的鼠标移动到这里&hellip;</a></p>
<p><a href="http://developer.mozilla.org/" onmouseover="oTooltip.append(event,'提示文字2');" onmousemove="oTooltip.follow(event);" onmouseout="oTooltip.remove();">&hellip;或者这里!!</a></p>
</body>
</html>
```

下面的例子演示了在进行拖拽操作时`onmousemove`的用法.

```html
<!doctype html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Draggable objects</title>
<script type="text/javascript">

var bMouseUp = true, oDragging, nMouseX, nMouseY, nStartX, nStartY, nZFocus = 100 /* the highest z-Index present in your page plus 1 */;

function dragDown(oPssEvt1) {
  var bExit = true, oMsEvent1 = oPssEvt1 || /* IE */ window.event;
  for (var iNode = oMsEvent1.target; iNode; iNode = iNode.parentNode) {
    if (iNode.className === "draggable") { bExit = false; oDragging = iNode; break; }
  }
  if (bExit) { return; }
  bMouseUp = false;
  nStartX = nStartY = 0;
  for (var iOffPar = oDragging; iOffPar; iOffPar = iOffPar.offsetParent) {
    nStartX += iOffPar.offsetLeft;
    nStartY += iOffPar.offsetTop;
  }
  nMouseX = oMsEvent1.clientX;
  nMouseY = oMsEvent1.clientY;
  oDragging.style.zIndex = nZFocus++;
  return false;
}

function dragMove(oPssEvt2) {
  if (bMouseUp) { return; }
  var oMsEvent2 = oPssEvt2 || /* IE */ window.event;
  oDragging.style.left = String(nStartX + oMsEvent2.clientX - nMouseX) + "px";
  oDragging.style.top = String(nStartY + oMsEvent2.clientY - nMouseY) + "px";
}

function dragUp() { bMouseUp = true; }

document.onmousedown = dragDown;
document.onmousemove = dragMove;
document.onmouseup = dragUp;

</script>
<style type="text/css">
.draggable {
  position: fixed;
  left: 0;
  top: 0;
  width: auto;
  height: auto;
  cursor: move;
}

#myDiv {
  width: 300px;
  height: 200px;
  left: 200px;
  top: 200px;
  background-color: #00ff00;
}
</style>
</head>

<body>

<div class="draggable" id="myDiv"><p>一个 Hello world!</p></div>
<div class="draggable" style="background-color:#aaaaaa;">又一个 hello world!</div>

</body>
</html>
```
