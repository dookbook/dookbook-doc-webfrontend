TOPICS: grid property

# CSS 属性: `grid`

**`grid`** 是一个CSS简写属性，可以用来设置以下属性：

**显式网格**属性 [**`grid-template-rows`**](/zh-hans/webfrontend/grid-template-rows_property)、
[**`grid-template-columns`**](/zh-hans/webfrontend/grid-template-columns_property) 和 [**`grid-template-areas`**](/zh-hans/webfrontend/grid-template-areas_property)。

**隐式网格**属性 [**`grid-auto-rows`**](/zh-hans/webfrontend/grid-auto-rows_property)、[**`grid-auto-columns`**](/zh-hans/webfrontend/grid-auto-columns_property)
和 [**`grid-auto-flow`**](/zh-hans/webfrontend/grid-auto-flow_property)。

**间距**属性 [**`grid-column-gap`**](/zh-hans/webfrontend/grid-column-gap_property) 和 [**`grid-row-gap`**](/zh-hans/webfrontend/grid-row-gap_property)。

!!! warn "注意"
    您仅可在一个 **`grid`** 属性中声明**显式**或**隐式网格**。与其他简写属性同样，若有次级属性未被声明，其将使用初始值。另外，尽管此简写声明无法设置网格的槽（**gutter**），槽会被该声明重置。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **grid-template** | 定义了 `grid-template`，其包含 `grid-template-columns`，`grid-template-rows`和 `grid-template-areas`。|
| **grid-template-rows / auto-flow && dense? grid-auto-columns?** | 通过 `grid-template-rows` 属性显式设置行轨道来设置自动流（`grid-template-columns` 属性设为 `none`），并通过 `grid-auto-columns` 明确该如何自动重复列轨道（同时`grid-auto-rows`属性设为 `auto`）。`grid-auto-flow` 属性也被相应的设置为 `column`，并可附有 `dense`。<br><br>所有其余 `grid` 次级属性被重置为初始值。|
| **auto-flow && dense? grid-auto-rows? / grid-template-columns** | 通过 `grid-template-columns` 属性显式设置列轨道来设置自动流（`grid-template-rows` 属性设为 `none`），并通过 `grid-auto-rows` 明确该如何自动重复行轨道（同时`grid-auto-columns`属性设为 `auto`）。`grid-auto-flow` 属性也被相应的设置为 `row`，并可附有 `dense`。<br><br>所有其余 `grid` 次级属性被重置为初始值。|

## 语法

```css
/* <'grid-template'> values */
grid: none;
grid: "a" 100px "b" 1fr;
grid: [linename1] "a" 100px [linename2];
grid: "a" 200px "b" min-content;
grid: "a" minmax(100px, max-content) "b" 20%;
grid: 100px / 200px;
grid: minmax(400px, min-content) / repeat(auto-fill, 50px);

/* <'grid-template-rows'> /
   [ auto-flow && dense? ] <'grid-auto-columns'>? values */
grid: 200px / auto-flow;
grid: 30% / auto-flow dense;
grid: repeat(3, [line1 line2 line3] 200px) / auto-flow 300px;
grid: [line1] minmax(20em, max-content) / auto-flow dense 40%;

/* [ auto-flow && dense? ] <'grid-auto-rows'>? /
   <'grid-template-columns'> values */
grid: auto-flow / 200px;
grid: auto-flow dense / 30%;
grid: auto-flow 300px / repeat(3, [line1 line2 line3] 200px);
grid: auto-flow dense 40% / [line1] minmax(20em, max-content);

/* Global values */
grid: inherit;
grid: initial;
grid: unset;
```

## 示例

```html
<div id="container">
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
#container {
  display: grid;
  grid: repeat(2, 60px) / auto-flow 80px;
}

#container > div {
  background-color: #8ca0ff;
  width: 50px;
  height: 50px;
}
```
