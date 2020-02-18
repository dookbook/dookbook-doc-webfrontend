TOPICS: <bdo>
        <bdo> dir attribute

# HTML 双向覆盖元素: `<bdo>`

**HTML `<bdo>` 双向覆盖元素** 用于覆盖当前文本的朝向，它使得字符按给定的方向排列。

!!! warn "注意"
    文字的字符是从起点沿给定方向绘制的；各个字符的方向不会受到影响（例如，字符不会向后绘制）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*、*短语内容*、*可触摸内容*。|
| **允许的内容** | *短语内容*。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** |接受*短语内容*的任何元素。|
| **允许的 ARIA 角色** |所有。 |
| **DOM 接口** | **`HTMLElement`** 包括Gecko 1.9.2（Firefox 4）之前的版本，Firefox都 **`HTMLSpanElement`** 为此元素实现了接口。 |

## 属性

这个标签包含 [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `dir` | 这个标签包含文本的文本方向. 属性值可为:<br><br>`ltr`: 从左往右写，与现代汉语的书写习惯相同.<br>`rtl`: 从右往左写，与古代汉语书写习惯相同. |

## 示例

```html
<!-- 改变文本方向 -->
<p>This text will go left to right.</p>
<p><bdo dir="rtl">This text will go right
to left.</bdo></p>
```

## 备注

HTML 4的规范文档中没有描述该元素的事件，它们在XHTML中被添加。这应该是当时的疏忽。
