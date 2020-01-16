TOPICS: Document.createNodeIterator
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createNodeIterator()`

返回一个新的 `NodeIterator` 对象.

!!! warn "译注"
    该函数的作用是用来筛选元素（节点）的。

## 语法

```javascript
var nodeIterator = document.createNodeIterator(root, whatToShow, filter);
```

| 参数 | 说明 |
| :-- | :-- |
| `root` | `NodeIterator`的起点，也就是筛选的范围，筛选`root`元素内的节点。 |
| `whatToShow` | 是一个可选的无符号长整形（`unsigned long`）数字去代表筛选的类型，也可是使用 `NodeFilter` 对象的常量来表示他表示筛选的元素类型。 默认值是 `0xFFFFFFFF` 代表 `SHOW_ALL` 常量. |
| `filter` | 是一个实现了`NodeFilte`r接口的对象; 它将基于`root`被子树中的每个节点调用其`acceptNode()`方法，该树被`whatToShow`标志接受，以确定是否将其包括在可迭代节点列表中（您可以使用一个简单的回掉函数 代替该方法）。 该方法必须返回以下常量之一：`NodeFilter.FILTER_ACCEPT`，`NodeFilter.FILTER_REJECT`或`NodeFilter.FILTER_SKIP`。 请参见示例。 |

!!! warn "Note"
    在Gecko 12.0（Firefox 12.0 / Thunderbird 12.0 / SeaMonkey 2.9）之前，此方法接受了可选的第四个参数（`entityReferenceExpansion`），
    它不是DOM4规范的一部分，因此已被删除。 此参数指示实体引用节点的子代是否对迭代器可见。 由于从未在浏览器中创建过这样的节点，因此此参数无效。

| 常量 | 数字值 | 描述 |
| :--- | :--- | :--- |
| `NodeFilter.SHOW_ALL` | `-1` (那是无符号long的最大值) | 显示所有节点。|
| `NodeFilter.SHOW_COMMENT` | `128` | 显示`Comment`节点。|
| `NodeFilter.SHOW_DOCUMENT` | `256` | 显示`Document`节点。|
| `NodeFilter.SHOW_DOCUMENT_FRAGMENT` | `1024` | 显示`DocumentFragment`节点。|
| `NodeFilter.SHOW_DOCUMENT_TYPE` | `512` | 显示`DocumentType`节点。|
| `NodeFilter.SHOW_ELEMENT` | `1` | 显示`Element`节点。 |
| `NodeFilter.SHOW_PROCESSING_INSTRUCTION` | `64` | 显示`ProcessingInstruction`节点。|
| `NodeFilter.SHOW_TEXT` | `4` | 显示`Text`节点。|

## 示例

```javascript
// 用于返回body元素下的所有p标签，并保存在pars列表中
var nodeIterator = document.createNodeIterator(
  document.body,
  NodeFilter.SHOW_ELEMENT,
  function(node) {
      return node.nodeName.toLowerCase() === 'p' ? NodeFilter.FILTER_ACCEPT : NodeFilter.FILTER_REJECT;
  }
);
var pars = [];
var currentNode;

while (currentNode = nodeIterator.nextNode()) {
  pars.push(currentNode);
}

```
