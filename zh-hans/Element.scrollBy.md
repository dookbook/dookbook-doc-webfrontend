TOPICS: Element.scrollBy
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollBy()`

**`scrollBy()`** 方法是使得元素滚动一段特定距离的 Element 接口。

## 语法

```javascript
element.scrollBy(x-coord, y-coord);
element.scrollBy(options)
```

- `x-coord` 是元素要在横轴上滚动的距离。
- `y-coord` 是元素要在纵轴上滚动的距离。

要么

- `options` 是一个 `ScrollToOptions` 字典。

## 示例

```javascript
// 让元素滚动
element.scrollBy(300, 300);
```

使用 options:

```javascript
element.scrollBy({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
