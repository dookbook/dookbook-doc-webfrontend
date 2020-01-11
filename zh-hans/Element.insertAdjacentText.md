TOPICS: Element.insertAdjacentText
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.insertAdjacentText()`

**`insertAdjacentText()`** 方法将一个给定的文本节点插入在相对于被调用的元素给定的位置。

## 语法

```javascript
element.insertAdjacentText(position, element);
```

| 参数 | 说明 |
| :-- | :-- |
| `position` | `DOMString`表示相对于元素的位置； 必须是以下字符串之一：<br>1. `'beforebegin'`: 在元素本身之前。<br>2. `'afterbegin'`: `ust`在元素中，在其第一个子元素之前。<br>3. `'beforeend'`: 在元素的最后一个子元素之后。<br>4. `'afterend'`: 在元素本身之后。|
| `element` | 一个`DOMString`，代表要插入树中的文本。 |

## 例外

| 例外 | 说明 |
| `SyntaxError` | 指定的位置不是可识别的值。|

## 职位名称的可视化

```html
<!-- beforebegin -->
<p>
<!-- afterbegin -->
foo
<!-- beforeend -->
</p>
<!-- afterend -->
```

!!! warn "注意"
    只有当节点位于树中并具有元素父元素时，`beforebegin`和`afterend`位置才能工作。

## 示例

```javascript
beforeBtn.addEventListener('click', function() {
  para.insertAdjacentText('afterbegin',textInput.value);
});

afterBtn.addEventListener('click', function() {
  para.insertAdjacentText('beforeend',textInput.value);
});
```
