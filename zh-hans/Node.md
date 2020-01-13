TOPICS: Node.prepend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.prepend()`

**`ParentNode.prepend`** 方法可以在父节点的第一个子节点之前插入一系列Node对象或者`DOMString`对象。`DOMString`会被当作`Text`节点对待（也就是说插入的不是HTML代码）。

## 语法

```javascript
Node.prepend((Node or DOMString)... nodes);
```

| 参数 | 说明 |
| :-- | :-- |
| `nodes` | 要插入的一系列`Node`或者`DOMString`。|

**返回值**: `undefined`

## 错误

- `HierarchyRequestError`：节点不能插入当前层级内。

## 示例

### 前置元素

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
var span = document.createElement("span");
parent.append(p);
parent.prepend(span);

console.log(parent.childNodes); // NodeList [ <span>, <p> ]
```

### 前置文字

```javascript
var parent = document.createElement("div");
parent.append("Some text");
parent.prepend("Headline: ");

console.log(parent.textContent); // "Headline: Some text"
```

### 附加元素和文字

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
parent.prepend("Some text", p);

console.log(parent.childNodes); // NodeList [ #text "Some text", <p> ]
```

### `Node.prepend()` 无法作用域

`prepend()`不能在`with`语句内使用

```javascript
var parent = document.createElement("div");

with(parent) {
  prepend("foo");
}
// ReferenceError: prepend is not defined
```

## Polyfill

使用下面的代码在IE9或更高版本中模拟prepend()方法：

```javascript
// from: https://github.com/jserz/js_piece/blob/master/DOM/ParentNode/prepend()/prepend().md
(function (arr) {
    arr.forEach(function (item) {
        item.prepend = item.prepend || function () {
            var argArr = Array.prototype.slice.call(arguments),
                docFrag = document.createDocumentFragment();

            argArr.forEach(function (argItem) {
                var isNode = argItem instanceof Node;
                docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
            });

            this.insertBefore(docFrag, this.firstChild);
        };
    });
})([Element.prototype, Document.prototype, DocumentFragment.prototype]);
```
