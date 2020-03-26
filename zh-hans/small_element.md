TOPICS: <small>

# HTML 小字号元素 `<small>`

HTML 中的 **`<small>`** 元素将使**文本的字体变小一号**。(例如从大变成中等，从中等变成小，从小变成超小)。在HTML 5中，除了它的样式含义，这个元素被重新定义为表示*边注释*和*附属细则*，包括*版权*和*法律文本*。
但，如果被包围的字体已经是字体模型所支持的最小字号，那么 `<small>` 标签将不起任何作用。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*。 |
| **允许的内容** | *短语内容* |
| **标签省略** | 无，必须拥有起始和结束标签。 |
| **允许的父元素** | 接受 *短语内容* 或者 *流式内容* 的任何元素。|
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

这个元素只有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 示例

## 原始示例

```html
<p>This is the first sentence.
  <small>This whole sentence is in small letters.</small>
</p>
```

## CSS 样式替代方案

```html
<p>This is the first sentence.
  <span style="font-size:0.8em;">This whole sentence is in small letters.</span>
</p>
```

## 注意事项

尽管 `<small>` 元素，和[`<b>`](/zh-hans/webfrontend/<b>) 元素和 [`<i>`](/zh-hans/webfrontend/<i>)
元素一样，被认为违反了结构和样式分离的原则，但是在HTML 5中是允许使用这三个元素的。读者应该自行判断使用
`<small>` 还是 [[CSS]]。
