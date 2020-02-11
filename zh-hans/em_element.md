TOPICS: <em>

# HTML着重元素：`<em>`

**HTML着重元素** (**`<em>`**) 标记出需要用户*着重阅读*的内容，`<em>`元素是可以*嵌套的*，嵌套层次越深，则其包含的内容被认定为越需要着重阅读。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*, *可触摸内容*。 |
| **允许的内容** | *短语内容*。|
| **标签省略** | 不允许，开始和结束标签都必需。 |
| **允许的父元素** | 任何可包含*短语内容*的元素。|
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

此元素只包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 示例

`<em>`元素通常被用于指示一个隐式或显式的对比。

```html
<p>
  In HTML 5, what was previously called <em>block-level</em> content is now called <em>flow</em> content.
</p>
```

## `<i>` 对比 `<em>`

在默认情况下，视觉效果是一样的这两个标签都把内容呈现为*斜体*. 但语义是不同的。 `<em>` 标签表示着重强调其内容，
而 *[`<i>`](/zh-hans/webfrontend/<i>)* 标签表示从正常的散文中区分出的文本，指的是一个字的定义，而不是其自身代表的语义。
(如果是电影或书籍的名字，一个外来词，则应该使用 *[`<cite>`](/zh-hans/webfrontend/<cite>)* )

例如，`<em>`可能是: "Just do it already!", 或: "We had to do something about it". 人或软件在阅读文本时会对斜体字的发音使用重读强调。

例如，[`<i>`](/zh-hans/webfrontend/<i>)可能是: "The Queen Mary sailed last night".
在这里没有必要对这个词"Queen Mary"添加强调或重要性. 它只是表明，谈论问题的对象不是一个名叫玛丽女王, 而是一艘名字叫玛丽的船.
另一个例子[`<i>`](/zh-hans/webfrontend/<i>)可能是: "The word the is an article".
