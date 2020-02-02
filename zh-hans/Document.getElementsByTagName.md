TOPICS: Document.getElementsByTagName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByTagName()`

返回一个包括所有给定标签名称的元素的HTML集合`HTMLCollection`。 整个文件结构都会被搜索，包括根节点。返回的 HTML集合是动态的,
意味着它可以自动更新自己来保持和 DOM 树的同步而不用再次调用 `document.getElementsByTagName()` 。

## 语法

```javascript
var elements = document.getElementsByTagName(name);
```

- `elements` 是一个由发现的元素出现在树中的顺序构成的动态的HTML集合 `HTMLCollection` (但是看下面的提示) 。

!!! warn "注意"
    最新的 W3C 规范 说明这些元素是 `HTMLCollection` (HTML集合); 然而, 这个方法在WebKit内核的浏览器中返回一个 `NodeList`.

| 参数 | 说明 |
| :-- | :-- |
| `name` | 是一个代表元素的名称的字符串。特殊字符 `"*"` 代表了所有元素。 |

## 示例

在以下的例子中，`getElementsByTagName()` 开始于一个具体的父级元素并且从它自上而下递归地在DOM树中搜索符合标签名称参数的子元素。

注意调用 `getElementsByTagName()` 的不是那个文件节点 `document`，事实上是使用这个方法 `element.getElementsByTagName()`。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>getElementsByTagName example</title>
  <script>
    function getAllParaElems() {
      var allParas = document.getElementsByTagName("p");
      var num = allParas.length;
      alert("There are " + num + " paragraph in this document");
    }

    function div1ParaElems() {
      var div1 = document.getElementById("div1");
      var div1Paras = div1.getElementsByTagName("p");
      var num = div1Paras.length;
      alert("There are " + num + " paragraph in #div1");
    }

    function div2ParaElems() {
      var div2 = document.getElementById("div2");
      var div2Paras = div2.getElementsByTagName("p");
      var num = div2Paras.length;
      alert("There are " + num + " paragraph in #div2");
    }
  </script>
</head>
<body style="border: solid green 3px">
  <p>Some outer text</p>
  <p>Some outer text</p>

  <div id="div1" style="border: solid blue 3px">
    <p>Some div1 text</p>
    <p>Some div1 text</p>
    <p>Some div1 text</p>

    <div id="div2" style="border: solid red 3px">
      <p>Some div2 text</p>
      <p>Some div2 text</p>
    </div>
  </div>

  <p>Some outer text</p>
  <p>Some outer text</p>

  <button onclick="getAllParaElems();">
    show all p elements in document</button><br />

  <button onclick="div1ParaElems();">
    show all p elements in div1 element</button><br />

  <button onclick="div2ParaElems();">
    show all p elements in div2 element</button>

</body>
</html>
```

## 注意

当在一个HTML 文件上执行时，`getElementsByTagName()` 会在执行前把参数转换为小写字母。这是试着在一个HTML文件的子树匹配驼峰命名法的 SVG 元素时不希望的.
`document.getElementsByTagNameNS()` 在那种情况下会有用.

`document.getElementsByTagName()` 类似于 `element.getElementsByTagName()`，除了它会搜索整个文档这点。
