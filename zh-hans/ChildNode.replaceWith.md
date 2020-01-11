TOPICS: ChildNode.replaceWith
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ChildNode.replaceWith()`

**`ChildNode.replaceWith()`** 的方法用一套 `Node` 对象或者 `DOMString` 对象，替换了该节点父节点下的子节点。`DOMString` 对象被当做等效的
`Text` 节点插入。

## 语法

```javascript
[Throws, Unscopable]
void ChildNode.replaceWith((Node or DOMString)... nodes);
```

| 参数 | 说明 |
| :-- | :-- |
| `nodes` | 一系列用来替换的 `Node` 对象或者 `DOMString` 对象。

## 例外

- `HierarchyRequestError`: 无法在层次结构中的指定点插入节点。

## 示例

### 使用 `replaceWith()`

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.replaceWith(span);

console.log(parent.outerHTML);
// "<div><span></span></div>"
```

### `ChildNode.replaceWith()` 无法确定范围

`replaceWith()` 的方法并没有作用于`with`语句.

```javascript
with(node) {
  replaceWith("foo");
}
// ReferenceError: replaceWith is not defined
Polyfill节
你可以在IE9及更高级的浏览器中使用下面的代码向上兼容replaceWith()的方法:

(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('replaceWith')) {
      return;
    }
    Object.defineProperty(item, 'replaceWith', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function replaceWith() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.parentNode.replaceChild(docFrag, this);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```
