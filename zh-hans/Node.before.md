TOPICS: Node.before
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.before()`

**`Node.before`** 方法可以在`ChildNode`这个节点的父节点中插入一些列的 `Node` 或者 `DOMString` 对象，位置就是在`ChildNode`节点的前面
`DOMString` 对象其实和 `Text`节点一样的方式来完成插入的。

语法

```javascript
[Throws, Unscopable]
void Node.before((Node or DOMString)... nodes);
```

| 参数 | 说明 |
| :-- | :-- |
| `nodes` | 一系列的 `Node` 或者 `DOMString`

## 例外情况

- `HierarchyRequestError`: 当节点插入了错误的层级就会出现报错，需要遵循HTML标签的层级关系，

## 示例

### 插入元素节点

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.before(span);

console.log(parent.outerHTML);
// "<div><span></span><p></p></div>"
```

### 插入文本节点

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);

child.before("Text");

console.log(parent.outerHTML);
// "<div>Text<p></p></div>"
```

### 同时插入文本和元素

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.before(span, "Text");

console.log(parent.outerHTML);
// "<div><span></span>Text<p></p></div>"
```

### `Node.before()` 不可使用区域

`before()` 不能配合`with`声明使用

```javascript
with(node) {
  before("foo");
}
// ReferenceError: before is not defined
```

## Polyfill

兼容ie9或者更高版本的方法，您可以使用以下代码在Internet Explorer 9和更高版本中填充`before()`方法：

```javascript
// from: https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/before()/before().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('before')) {
      return;
    }
    Object.defineProperty(item, 'before', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function before() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.parentNode.insertBefore(docFrag, this);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```
