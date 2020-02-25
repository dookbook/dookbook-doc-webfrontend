TOPICS: overflow-wrap property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         夏凌晨; xgqfrms@mozilla.net; mdn:xgqfrms
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz

# CSS 属性: `overflow-wrap`

CSS 属性 **`overflow-wrap`** 是用来说明**当一个不能被分开的字符串太长而不能填充其包裹盒时**，**为防止其溢出**，浏览器是否允许这样的单词中断换行。

!!! warn "注意"
    与 [*`word-break`*](/zh-hans/webfrontend/word-break_property) 不同，如果整个单词不能被放置在它自己的行上而不发生溢出，那么`overflow-wrap`只会创建一个断行符。

该属性最初是一个名为`word-wrap`的非标准、无前缀的Microsoft扩展，由大多数同名浏览器实现。此后，它被重命名为`overflow-wrap`，其中`word-wrap`是一个别名。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 表示在正常的单词结束处换行。|
| **`break-word`** | 表示如果行内没有多余的地方容纳该单词到结尾，则那些正常的不能被分割的单词会被强制分割换行。|

## 示例

```css
p {
  width: 13em;
  background: gold;
}

p {
  width: 13em;
  background: gold;
  overflow-wrap: break-word;
}
```
