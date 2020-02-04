TOPICS: onreset
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onreset`

**`onreset`** 属性包含 `EventHandler` ，当收到一个 `reset` 事件时触发

## 语法

```javascript
window.onreset = funcRef;
```

- `funcRef` 是一个函数的引用.

## 备注

`reset` 事件只有在用户点击表单中的reset按钮时才会被触发 (`<input type="reset"/>`).

## 示例

```html
<html>
<script>
function reg() {
  window.captureEvents(Event.RESET);
  window.onreset = hit;
}

function hit() {
 alert('hit');
}
</script>

<body onload="reg();">
 <form>
   <input type="reset" value="reset" />
 </form>
 <div id="d"> </div>
</body>
</html>
```
