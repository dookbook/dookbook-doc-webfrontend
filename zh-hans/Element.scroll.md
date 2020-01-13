TOPICS: Element.scroll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scroll()`

**`scroll()`** 方法是用于在给定的元素中滚动到某个特定坐标的 `Element` 接口。

## 语法

```javascript
element.scroll(x-coord, y-coord)
element.scroll(options)
```

- `x-coord` 是指在元素左上方区域横轴方向上想要显示的像素。
- `y-coord` 是指在元素左上方区域纵轴方向上想要显示的像素。

要么

- `options` 是一个 `ScrollToOptions` 的字典。

## 示例

```javascript
// 在元素上方显示1000像素
element.scroll(0, 1000);
```

使用 `options`:

```javascript
element.scroll({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
