TOPICS: Document.getElementsByTagNameNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByTagNameNS()`

返回带有指定名称和命名空间的元素集合。整个文件结构都会被搜索，包括根节点。

## 语法

```javascript
elements = document.getElementsByTagNameNS(namespace, name)
```

- `elements` 是一个在树中按顺序查询到的动态的HTML集合 `HTMLCollection` (但是看下面的提示)。

| 参数 | 说明 |
| :-- | :-- |
| `namespace` | 是所要查询的元素的命名空间URL。 |
| `name` | 是所要查询的元素的名称。其中特殊字符 `"*"` 代表所有元素 |

!!! warn "注意"
    在W3C文档中，`elements`是一个`NodeList`，而该方法在Gecko内核的浏览器和IE中返回的是HTML集合`HTMLCollection`. Opera返回的也是一个 `NodeList`，
    但通过`namedItem`方法 ， 使得它类似于一个`HTMLCollection` . 截止2012年1月，只有WebKit内核的浏览器返回的值是一个纯 `NodeList`.

## 示例

在下面的示例中，`getElementsByTagNameNS`方法从一个特定的父元素开始，并从该父元素的DOM中自上而下递归式搜索，查找所有与标签名参数匹配的子元素 。

注意当调用`getElementsByTagName`方法获取到的节点不是文档节点时，实际上是调用了`element.getElementsByTagNameNS`方法 。

需要使用以下示例，只需复制/粘贴以下代码到用.XHTML后缀名保存的新文件中即可。

```html
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
<title>getElementsByTagNameNS example</title>

<script type="text/javascript">

function getAllParaElems()
{
  var allParas = document.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = allParas.length;

  alert("There are " + num + " &lt;p&gt; elements in this document");
}


function div1ParaElems()
{
  var div1 = document.getElementById("div1")
  var div1Paras = div1.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = div1Paras.length;

  alert("There are " + num + " &lt;p&gt; elements in div1 element");
}


function div2ParaElems()
{
  var div2 = document.getElementById("div2")
  var div2Paras = div2.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = div2Paras.length;

  alert("There are " + num + " &lt;p&gt; elements in div2 element");
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

## 针对其他不支持此方法的浏览器的解决方法

如果所使用的浏览器不支持此方法，可使用另一种方法（例如遍历所有子元素的DOM，识别所有@xmlns实例等等）来查找所有具有本地名称和命名空间的标签，但此方法更快。 (为了兼容 Explorer,
在下面的函数中，你可以调用一个XPath包, 而不仅仅是 XPath (由于 Explorer 支持不同API的XPath ), 例如 this wrapper class.)

```javascript
function getElementsByTagNameNSWrapper (ns, elName, doc, context) {
  if (!doc) {
    doc = document;
  }
  if (!context) {
    context = doc;
  }

  var result = doc.evaluate('//*[local-name()="'+elName+'" and namespace-uri() = "'+ns+'"]', context, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE, null);

    var a = [];
    for(var i = 0; i < result.snapshotLength; i++) {
        a[i] = result.snapshotItem(i);
    }
    return a;
}
```
