TOPICS: Element.scrollTo
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollTo()`

`Element` 的 **`scrollTo()`** 方法可以使界面滚动到给定元素的指定坐标位置。

## 语法

```javascript
element.scrollTo(x-coord, y-coord)
element.scrollTo(options)
```

- `x-coord` 是期望滚动到位置水平轴上距元素左上角的像素。
- `y-coord` 是期望滚动到位置竖直轴上距元素左上角的像素。

要么

- `options` 是一个`ScrollToOptions`对象。

## 示例

```javascript
element.scrollTo(0, 1000);
```

使用 `options`:

```javascript
element.scrollTo({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
