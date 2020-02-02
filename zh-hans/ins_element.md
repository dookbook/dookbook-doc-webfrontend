TOPICS: <ins>
        <ins> cite attribute
        <ins> datetime attribute

# HTML 插入文本元素 `<ins>`

**HTML `<ins>` 元素**标记已经被**插入文档中的文本**。你可以使用 *[`<del>`](/zh-hans/webfrontend/<del>)* 元素来标记文档中删除的文本。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *短语内容* 或者 *流式内容*。|
| **允许内容** | *透明内容*。|
| **标签闭合** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父级标签** | 任意*短语内容* |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLModElement`** |

## 属性

该元素支持所有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)，除此以外还支持下列属性：

| 属性 | 描述 |
| :-- | :-- |
| **`cite`** | 指向一个文档的 URL，该文档解释了文本被插入或修改的原因。（目前该属性还没有被主流浏览器支持） |
| **`datetime`** | 指示此修改发生的时间和日期，并且该特性的值必须是一个有效的日期或者时间字符串。如果该值不能被解析为日期或者时间，则该元素不具有相关联的时间标记。 |

## 示例

```html
<ins>这一段文本是新插入至文档的。</ins>

<ins cite="https://dookbook.info/zh-hans/webfrontend/<ins>/">
  这一段文本是新插入至文档的。</ins>
```
