TOPICS: Element.getAttributeNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNode()`

返回指定元素的指定属性， 返回值是 `Attr` 节点类型

## 语法

```javascript
var attrNode = element.getAttributeNode(attrName);
```

- `attrNode`  获得的属性返回值，是 `Attr` 节点，`nodeType` 为 `2`
- `attrName` 是一个包含属性名称的 字符串

## 例外情况

- `HierarchyRequestError`: 在某些不正确的层级结构进行了插入操作。

## 示例

```javascript
// html: <div id="top" />
var t = document.getElementById("top");
var idAttr = t.getAttributeNode("id");
alert(idAttr.value == "top")
```
