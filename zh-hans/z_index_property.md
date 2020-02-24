TOPICS: z-index property

# CSS 属性: `z-index`

**`z-index`** 属性设定了一个定位元素及其后代元素或 `flex` 项目的 `z-order`。当元素之间重叠的时候，`z-index` 较大的元素会覆盖较小的元素在上层进行显示。

对于一个已经定位的盒子（即其 `position` 属性值不是 `static`，这里要注意的是 CSS 把元素看作盒子），`z-index` 属性指定：

1. 盒子在当前堆叠上下文中的堆叠层级。
1. 盒子是否创建一个本地堆叠上下文。

`z-index` 属性可以被设定为关键词 `auto` 或 `<integer>`。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| `auto` | 默认。堆叠顺序与父元素相等。|
| `<integer>` | `<integer>`（整型数字）是生成的盒子在当前堆叠上下文中的堆叠层级。此盒子也会创建一个堆叠层级为 `0` 的本地堆叠上下文。这意味着后代（元素）的 `z-indexes` 不与此元素外的其他元素的 `z-indexes` 进行对比。

## 示例

```html
<div class="dashed-box">Dashed box
  <span class="gold-box">Gold box</span>
  <span class="green-box">Green box</span>
</div>
```

```css
.dashed-box {
  position: relative;
  z-index: 1;
  border: dashed;
  height: 8em;
  margin-bottom: 1em;
  margin-top: 2em;
}
.gold-box {
  position: absolute;
  z-index: 3; /* put .gold-box above .green-box and .dashed-box */
  background: gold;
  width: 80%;
  left: 60px;
  top: 3em;
}
.green-box {
  position: absolute;
  z-index: 2; /* put .green-box above .dashed-box */
  background: lightgreen;
  width: 20%;
  left: 65%;
  top: -25px;
  height: 7em;
  opacity: 0.9;
}
```
