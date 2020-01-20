TOPICS: Document.createTextNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createTextNode()`

创建一个新的文本节点。这个方法可以用来转义 HTML 字符。

## 语法

```javascript
var text = document.createTextNode(data);
```

- `text` 是一个文本节点。
- `data` 是一个字符串，包含了要放入文本节点的内容。

## 示例

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<title>createTextNode 示例</title>
</head>

<body>
  <button value="好耶！">好耶！</button>
  <button value="坏耶！">坏耶！</button>
  <button value="Rikka! ">Rikka!</button>
  <button value="日卡卡！">日卡卡！</button>

  <hr />

  <p id="p1">段落的第一行。</p>

  <script>
  const p1 = document.getElementById("p1"),
  buttons = document.body.querySelectorAll(":scope > button");
  function addTextNode(text) {
    p1.appendChild( document.createTextNode(text) );
  }
  buttons.forEach(button =>
    button.addEventListener("click", () =>
      addTextNode(button.value)
    )
  );
  </script>
</body>
</html>
```
