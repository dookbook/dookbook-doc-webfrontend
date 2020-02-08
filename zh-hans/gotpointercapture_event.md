TOPICS: ongotpointercapture
        gotpointercapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `gotpointercapture` 事件

**`ongotpointercapture`** 事件是`GlobalEventHandlers`的属性,这个事件返回`gotpointercapture`类型的事件操作。

## 语法

```javascript
window.ongotpointercapture = functionReference
```

## 示例

```html
<html>
<script>
function overHandler(ev) {
 // Determine the target event's gotpointercapture handler
 var gotCaptureHandler = ev.target.ongotpointercapture;
}
function init() {
 var el=document.getElementById("target");
 el.ongotpointercapture = overHandler;
}
</script>
<body onload="init();">
<div id="target"> Touch me ... </div>
</body>
</html>
```
