TOPICS: <del>
        <del> cite attribute
        <del> datetime attribute

# HTML 删除文本元素 `<del>`

**HTML `<del>` 元素**标记从文档中**删除的文本内容**。比如可以在需要显示修改记录或者源代码差异的情况使用这个标签。
*[`<ins>`](/zh-hans/webfrontend/<ins>)* 的作用恰恰于此相反：表示文档中添加的内容。

这个标签通常（但不一定要）在文字上显示*删除线* (CSS中 *`text-decoration: line-through`*)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *短语内容* 或者 *流式内容*。|
| **允许的内容** | 透明内容 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任意接受*短语内容*的元素 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLModElement`** |

## 属性

这个标签包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`cite`** | 修改的原因的链接地址URL（比如：根据某次会议讨论）。 |
| **`datetime`** | 修改的时间和日期，这里的时间和日期格式要符合规范。如果设置的值不符合该规范，那么它将没有任何意义。 |

## 示例

```html
<p><del>This text has been deleted</del>, here is the rest of the paragraph.</p>
<del ><p >This paragraph has been deleted.</p ></del >
```
