TOPICS: hidden attribute

# HTML 全局属性: `hidden`

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) **`hidden`** 用来隐藏元素。可以对 `hidden` 属性进行设置，
使用户在满足某些条件时才能看到某个元素（比如选中**复选框**，等等）。然后可使用 JavaScript 来删除 `hidden` 属性，使该元素变得可见。

隐藏元素不应与非隐藏元素链接，作为隐藏元素的后代的元素仍然是活动的，这意味着脚本元素仍然可以执行，表单元素仍然可以提交。

比如说，用 *`href`* 标签链接到一个带有 `hidden` 标签的区块是不对的。如果这个区块和这个页面不相干，或者这个区块不适用于这个页面，那没有任何理由需要链接到它。

!!! warn "说明"
    CSS的 *`display`* 属性可以覆盖具有 `hidden` 属性的元素。例如: 元素被设置为 *`display: flex`* 将会导致元素显示出来，尽管设置了`hidden`属性

## 示例

```html
<p hidden>这是一段隐藏的段落。</p>
<p>这是一段可见的段落。</p>
```
