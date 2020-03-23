TOPICS: box-sizing property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `box-sizing`

CSS 中的 **`box-sizing`** 属性设置**如何计算一个元素**的**总宽度**和**总高度**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`content-box`** | 默认值，标准盒子模型。`width` 与 `height` 只包括内容的宽和高， 不包括边框（`border`），内边距（`padding`），外边距（`margin`） |
| **`border-box`** | `width` 和 `height` 属性包括内容，内边距和边框，但不包括外边距 |

## 示例

本例显示了不同的 `box-sizing` 值如何改变两个原本相同的元素的渲染尺寸。

```css
div {
  width: 160px;
  height: 80px;
  padding: 20px;
  border: 8px solid red;
  background: yellow;
}

.content-box {
  box-sizing: content-box;
  /* 总宽: 160px + (2 * 20px) + (2 * 8px) = 216px
  总高: 80px + (2 * 20px) + (2 * 8px) = 136px
  内容框宽度: 160px
  内容框高度: 80px */
}

.border-box {
  box-sizing: border-box;
  /* 总宽: 160px
  总高: 80px
  内容框宽度: 160px - (2 * 20px) - (2 * 8px) = 104px
  内容框高度: 80px - (2 * 20px) - (2 * 8px) = 24px */
}
```

```html
<div class="content-box">Content box</div>
<br>
<div class="border-box">Border box</div>
```
