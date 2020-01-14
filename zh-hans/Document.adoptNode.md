TOPICS: Document.adoptNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.adoptNode()`

从其他的`document`文档中获取一个节点。 该节点以及它的子树上的所有节点都会从原文档删除 (如果有这个节点的话), 并且它的`ownerDocument` 属性会变成当前的document文档。
之后你可以把这个节点插入到当前文档中。

## 语法

```javascript
node = document.adoptNode(externalNode);
```

| 参数 | 说明 |
| :-- | :-- |
| `node` | 导入当前文档的新节点. 新节点的 `parentNode` 是 `null`, 因为它还没有插入当前文档的文档树中,属于游离状态.
| `externalNode` | 将要从外部文档导入的节点。

## 示例

```javascript
// 该函数用来从本文档的第一个iframe中获取第一个element元素，
// 并插入到当前文档树中
function getEle(){
  var iframe = document.getElementsByTagName("iframe")[0],
    ele = iframe.contentWindow.document.body.firstElementChild
    if(ele){
      document.body.appendChild(document.adoptNode(ele))
    }else{
      alert("没有更多元素了")
    }
}
document.getElementById("move").onclick = getEle
```

```javascript
// index.html

<!DOCTYPE html>
<html>
<head>
    <title>index.html</title>
</head>
<body>
    <iframe src="iframe.html"></iframe>
    <button id="move">移动元素</button>
</body>
</html>

// iframe.html

<!DOCTYPE html>
<html>
<head>
    <title>iframe.html</title>
</head>
<body>
    <h1>Hello</h1><h3>My world!</h3>
</body>
</html>
```

## 笔记

有时候调用`adopNode`可能会失败因为节点资源来自不同的源，但是这不应该是浏览器的实现问题。

通常，由于源节点来自不同的实现，所以`acceptNode`调用可能会失败，但是，这对于浏览器实现而言应该不是问题。

!!! warn "译者注"
    该方法不但可以从`iframe`中获取`adopt`元素，在同一`document`文档下的不同两个元素中也可以使用，该方法可以实现从左边栏列表中选取某些元素加载到右边栏的功能。

将外部文档的节点插入当前文档之前,你必须使用 `document.importNode()` 从外部文档导入源节点,或者使用 `document.adoptNode()` 导入源节点,
想要了解更多的 `Node.ownerDocument` 问题,请参考 [W3C DOM FAQ](http://www.w3.org/DOM/faq.html#ownerdoc).

即使你不执行导入动作,就执行插入外部文档中的节点.Firefox目前也不会报错(如果严格按标准执行,很多已有的网站都无法正常运行). 我们鼓励开发者严格按标准修改自己已有的不符合上述标准的代码.
