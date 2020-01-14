TOPICS: Document.createAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createAttribute()`

**`Document.createAttribute()`** 方法创建并返回一个新的属性节点。这个对象创建一个实现了 `Attr` 接口的节点。这个方式下DOM不限制节点能够添加的属性种类。

## 语法

```javascript
attribute = document.createAttribute(name)
```

| 参数 | 说明 |
| :-- | :-- |
| `name` | 属性的属性名 |

**返回值**: 一个 `Attr` 节点。

## 异常

- `INVALID_CHARACTER_ERR` 如果参数含有非法的XML属性字符。

## 示例

```javascript
var node = document.getElementById("div1");
var a = document.createAttribute("my_attrib");
a.value = "newVal";
node.setAttributeNode(a);
console.log(node.getAttribute("my_attrib")); // "newVal"
```

## 备注

该方法的返回值是一个类型为 `Attr` 的节点。你可以通过为该节点的 `nodeValue` 属性赋值来设置该属性节点的属性值，也可以使用常用的 `setAttribute()` 方法来替代该方法.
