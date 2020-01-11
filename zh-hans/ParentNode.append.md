TOPICS: ParentNode.append
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ParentNode.append()`

**`ParentNode.append`** 方法在 `ParentNode` 的最后一个子节点之后插入一组 `Node` 对象或 `DOMString` 对象。
被插入的 `DOMString` 对象等价为 `Text` 节点。
与 `Node.appendChild()` 的差异：

- `ParentNode.append()`允许追加  `DOMString` 对象，而 `Node.appendChild()` 只接受 `Node` 对象。
- `ParentNode.append()` 没有返回值，而 `Node.appendChild()` 返回追加的 `Node` 对象。
- `ParentNode.append()` 可以追加多个节点和字符串，而 `Node.appendChild()` 只能追加一个节点。

## 语法

```javascript
[Throws, Unscopable]
void ParentNode.append((Node or DOMString)... nodes);
```

| 参数 | 说明 |
| :-- | :-- |
| `nodes` | 一组要插入的 `Node` 或 `DOMString` 对象。

## 例外情况

- `HierarchyRequestError`: 在层次结构中的指定点不能插入节点。

## 示例

### 插入一个元素节点

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
parent.append(p);

console.log(parent.childNodes); // NodeList [ <p> ]
插入文本节
var parent = document.createElement("div");
parent.append("Some text");

console.log(parent.textContent); // "Some text"
```

插入一个节点，同时插入一些文本

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
parent.append("Some text", p);

console.log(parent.childNodes); // NodeList [ #text "Some text", <p> ]
```

### `ParentNode.append()` 方法在 `with` 语句中不生效

为了保证向后兼容，`append` 方法在 `with` 语句中会被特殊处理，详情请看 `Symbol.unscopables`。

```javascript
var parent = document.createElement("div");

with(parent) {
  append("foo");
}
// ReferenceError: append is not defined
```

## Polyfill

下面的 Polyfill 只支持到 IE 9  及以上：

```javascript
// Source: https://github.com/jserz/js_piece/blob/master/DOM/ParentNode/append()/append().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('append')) {
      return;
    }
    Object.defineProperty(item, 'append', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function append() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.appendChild(docFrag);
      }
    });
  });
})([Element.prototype, Document.prototype, DocumentFragment.prototype]);
```
