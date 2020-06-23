TOPICS: gap property

# CSS 属性: `gap`

CSS **`gap`** 属性是用来设置**网格行与列之间的间隙**（gutters），该属性是 [**`row-gap`**](/zh-hans/webfrontend/row-gap_property)
和 [**`column-gap`**](/zh-hans/webfrontend/column-gap_property) 的简写形式。

```css
grid-gap: 0;
grid-gap: 10%;
grid-gap: 1em;
grid-gap: 10px 20px;
grid-gap: calc(20px + 10%);
```

!!! warn ""
    CSS Grid Layout 起初是用 **`grid-gap`** 属性来定义的，目前逐渐被 **`gap`** 替代。但是，为了兼容那些不支持 **`gap`** 属性的浏览器，你需要像上面的例子一样，使用带有前缀的属性。

该属性用来表示 [**`row-gap`**](/zh-hans/webfrontend/row-gap_property) 和 [**`column-gap`**](/zh-hans/webfrontend/column-gap_property)
的值，而 [**`column-gap`**](/zh-hans/webfrontend/column-gap_property) 是可选的，假如 [**`column-gap`**](/zh-hans/webfrontend/column-gap_property)
缺失的话，则会被设置成跟[**`row-gap`**](/zh-hans/webfrontend/row-gap_property) 一样的的值。

[**`row-gap`**](/zh-hans/webfrontend/row-gap_property) 和 [**`column-gap`**](/zh-hans/webfrontend/column-gap_property)
都可以用**length** 或者 **percentage** 来表示。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 网格线之间的间隙宽度。|
| **percentage** | 网格线直接的间隙宽度，相对网格容器的百分比。|

## Flex布局

```html
<div id="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#flexbox {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  gap: 20px 5px;
}

#flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 1 1 auto;
  width: 100px;
  height: 50px;
}
```

## Grid布局

```html
<div id="grid">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

```css
#grid {
  display: grid;
  height: 200px;
  grid-template: repeat(3, 1fr) / repeat(3, 1fr);
  gap: 20px 5px;
}

#grid > div {
  background-color: lime;
}
```
