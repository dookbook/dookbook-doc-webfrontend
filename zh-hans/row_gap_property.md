TOPICS: row-gap property

# CSS 属性: `row-gap`

CSS **`row-gap`** 属性用来设置**行元素之间的间隙大小**。

!!! warn "注意"
    CSS Grid Layout 起初是用 **`grid-row-gap`** 属性来定义的，目前逐渐被 **`row-gap`** 替代。但是，为了兼容那些不支持 **`row-gap`**
    属性的浏览器，你需要使用带有前缀的属性。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **length-percentage** | 表示行之间的间隔宽度。 **percentage** 表示相对栅格容器的百分比。 |

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
  row-gap: 20px;
}

#flexbox > div {
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
</div>
```

```css
#grid {
  display: grid;
  height: 200px;
  grid-template-columns: 200px;
  grid-template-rows: repeat(3, 1fr);
  row-gap: 20px;
}

#grid > div {
  background-color: lime;
}
```
