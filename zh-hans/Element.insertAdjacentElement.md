TOPICS: Element.insertAdjacentElement
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.insertAdjacentElement()`

**`insertAdjacentElement()`** 方法将一个给定的元素节点插入到相对于被调用的元素的给定的一个位置。

## 语法

```javascript
element.insertAdjacentElement(position, element);
```

| 参数 | 说明 |
| :-- | :-- |
| `position` | 一个 `DOMString` 表示相对于该元素的位置；必须是以下字符串之一：<br>1. `'beforebegin'`: 在该元素本身的前面.<br>2. `'afterbegin'`:只在该元素当中, 在该元素第一个子孩子前面.<br>3. `'beforeend'`:只在该元素当中, 在该元素最后一个子孩子后面.<br>4. `'afterend'`: 在该元素本身的后面.
| `element` | 要插入到树中的元素.

**返回值**: 插入的元素，插入失败则返回`null`.

## 异常

| 异常 | 说明 |
| :-- | :-- |
| `SyntaxError` | 插入的位置是一个无法识别的值。|
| `TypeError` | 插入的元素不是一个有效元素。|

## 位置命名的可视化展示

```html
<!-- beforebegin -->
<p>
<!-- afterbegin -->
foo
<!-- beforeend -->
</p>
<!-- afterend -->
```

!!! warn "注"
    当节点处于DOM树中而且有一个父元素的时候 `beforebegin` 和 `afterend`操作才能起作用。

## 示例

```javascript
beforeBtn.addEventListener('click', function() {
  var tempDiv = document.createElement('div');
  tempDiv.style.backgroundColor = randomColor();
  activeElem.insertAdjacentElement('beforebegin',tempDiv);
  setListener(tempDiv);
});

afterBtn.addEventListener('click', function() {
  var tempDiv = document.createElement('div');
  tempDiv.style.backgroundColor = randomColor();
  activeElem.insertAdjacentElement('afterend',tempDiv);
  setListener(tempDiv);
});
```
