TOPICS: grid-auto-rows property

# CSS 属性: `grid-auto-rows`

CSS属性 **`grid-auto-rows`** 用于指定隐式创建的行**轨道大小**。

如果定位到某行中的网格元素没有使用 `grid-template-rows` 来指定大小，则会隐式创建 `grid` 轨道来保存它。这可能在显示定位到超出范围的行，或者由自动放置算法创建额外的行时发生。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 一个非负的长度。|
| **percentage** | 相对于网格窗口块尺寸的非负 `percentage` 值。如果网格容器的块尺寸是不确定的, 则百分比值将被视为 `auto`。|
| **flex** | 非负的、以 `fr` 为单位的维度指定轨道的弹性因子。每个 `flex`-尺寸的轨道都按其弹性因子的比例挤占剩余空间的一部分。<br>当使用在 minmax() 符号外时，意味着最小值为 `auto` (例： minmax(`auto`, `flex`))。|
| **`max-content`** | 关键词，指明由网格元素中占用空间最大的那一个来决定轨道的尺寸。|
| **`min-content`** | 关键词，指明由网格元素中占用空间最小的那一个来决定轨道的尺寸。|
| **`minmax(min, max)`** | 函数符号，定义一个不小于min且不大于max的尺寸范围。如果max比min小，则max会被忽略，函数会被录作min处理。作为最大值，`flex` 值设置了轨道的弹性因子。作为最小值，会被当作0处理（或者最小内容——当网格容器指定了尺寸为最小内容）。|
| **`auto`** | 关键字，当用来指定最大值时与最大内容一致，当用来指定最小值时，它表示轨道中所有网格元素最小尺寸中的最大值（由min-width/min-height指定）。

!!! warn "注意"
    **`auto`** 轨道尺寸（且仅有 **`auto`** 轨道尺寸）可配合 [**`align-content`**](/zh-hans/webfrontend/align-content)
    和 [**`justify-content`**](/zh-hans/webfrontend/justify-content) 属性使用。

## 示例

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
</div>
```

```css
#grid {
  width: 200px;
  display: grid;
  grid-template-areas: "a a";
  grid-gap: 10px;
  grid-auto-rows: 100px;
}

#grid > div {
  background-color: lime;
}
```
