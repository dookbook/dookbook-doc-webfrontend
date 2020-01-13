TOPICS: Node.after
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.after()`

在其父节点的子节点列表中插入一些 `Node` 或 `DOMString` 对象。插入位置为该节点之后。`DOMString` 对象会被以 `Text` 的形式插入。

## 语法

```javascript
[Throws, Unscopable]
void Node.after((Node or DOMString)... nodes);
```

| 参数 | 说明 |
| :-- | :-- |
| `nodes` | 一组准备插入的 `Node` 或 `DOMString` 。

## 例外情况

- `HierarchyRequestError`: 在某些不正确的层级结构进行了插入操作。

## 示例

### 插入元素

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.after(span);

console.log(parent.outerHTML);
// "<div><p></p><span></span></div>"
```

### 插入文本

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);

child.after("Text");

console.log(parent.outerHTML);
// "<div><p></p>Text</div>"
```

### 同时插入元素和文本

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.after(span, "Text");

console.log(parent.outerHTML);
// "<div><p></p><span></span>Text</div>"
```

### `Node.after()` 会被 `with` 环境排除

`after()` 方法不在 `with` 环境的范围内，可以查看 `Symbol.unscopables` 来了解更多信息。

```javascript
with(node) {
  after("foo");
}
// ReferenceError: after is not defined
```
