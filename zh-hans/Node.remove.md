TOPICS: Node.remove
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.remove()`

**`Node.remove()`** 方法，把对象从它所属的 DOM 树中删除。

## 语法

```javascript
node.remove();
```

## 示例

### 使用 `remove()`

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<div id="div-03">Here is div-03</div>
```

```javascript
var el = document.getElementById('div-02');
el.remove();
// id 为 'div-02' 的 div 被删掉了
```

### `Node.remove()` 是不可见的

在 `with` 语句中，`remove()` 方法是不可见的。

```javascript
with(node) {
  remove();
}
// ReferenceError: remove is not defined
```

## Polyfill

您可以使用以下代码在Internet Explorer 9和更高版本中填充`remove()`方法：

```javascript
//https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/remove()/remove().md
(function (arr) {
   arr.forEach(function (item) {
    if (item.hasOwnProperty('remove')) {
      return;
    }
    Object.defineProperty(item, 'remove', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function remove() {
        this.parentNode.removeChild(this);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```
