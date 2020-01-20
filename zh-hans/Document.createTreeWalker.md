TOPICS: Document.createTreeWalker

# `Document.createTreeWalker()`

**`Document.createTreeWalker()`** 创建者方法返回一个新创建的`TreeWalker`对象。

## 语法

```javascript
document.createTreeWalker(root, whatToShow[, filter[, entityReferenceExpansion]]);
```

| 参数 | 说明 |
| :-- | :-- |
| `root` | 此`TreeWalker`遍历的根`Node`。通常，这将是文档拥有的元素。 |
| `whatToShow` 可选的 | 代表位掩码的`unsigned long`（无符号长），是通过组合`NodeFilter`的常量属性而创建的。 这是对某些类型的节点进行过滤的便捷方法。默认为`0xFFFFFFFF`，表示`SHOW_ALL`常量。 |
| `filter` 可选的 | 一个`NodeFilter`，是一个带有方法`acceptNode`的对象，由`TreeWalker`调用以确定是否接受通过`whatToShow`检查的节点。 |

## `whatToShow` 参数支持的值

| 常量 | 数值 | 说明 |
| `NodeFilter.SHOW_ALL` | `-1`（这是`unsigned long`的最大值） | 显示所有节点. |
| `NodeFilter.SHOW_COMMENT` | 128 | 显示"评论"节点. |
| `NodeFilter.SHOW_DOCUMENT` | 256 | 显示`Document`节点. |
| `NodeFilter.SHOW_DOCUMENT_FRAGMENT` | 1024 | 显示`DocumentFragment`节点. |
| `NodeFilter.SHOW_DOCUMENT_TYPE` | 512 | 显示`DocumentType`节点. |
| `NodeFilter.SHOW_ELEMENT` | 1 | 显示`Element`节点. |
| `NodeFilter.SHOW_PROCESSING_INSTRUCTION` | 64 | 显示`ProcessingInstruction`节点. |
| `NodeFilter.SHOW_TEXT` | 4 | 显示`Text`节点. |

**返回值**: 一个新的`TreeWalker`对象。

## 示例

下面的示例遍历身体中的所有节点，将节点集简化为元素，简单地通过可接受的每个节点（它可以在`acceptNode()`方法中简化该集）
相反），然后利用树遍历器迭代器创建该遍历器，以遍历节点（现在是所有元素）并将其推入数组。

```javascript
var treeWalker = document.createTreeWalker(
  document.body,
  NodeFilter.SHOW_ELEMENT,
  { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
  false
);

var nodeList = [];

while(treeWalker.nextNode()) nodeList.push(treeWalker.currentNode);
```
