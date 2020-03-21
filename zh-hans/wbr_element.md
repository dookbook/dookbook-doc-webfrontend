TOPICS: <wbr>

# HTML 单词换行时机元素 `<wbr>`

**HTML `<wbr>` 元素**  — 如果单词太长，或者您担心浏览器会在错误的位置**换行**，那么您可以使用它来添加*单词换行时机*。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*。|
| **允许的内容** | 空 |
| **标签遗漏** | 它是一个 **[空元素](/zh-hans/webfrontend/Empty_Element)**；它必须具有开始标签，但不能具有结束标签。|
| **允许的父元素** | 任何接受 *短语内容* 的元素。|
| **允许的 ARIA 角色** | 任何 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

这个元素仅仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)

## 使用须知

在 *[[UTF-8]]* 编码的页面中，`<wbr>` 表现为 *`U+200B ZERO-WIDTH SPACE`* （*零宽空格*）代码点。特别是，它表现为 *Unicode bidi BN* 代码点，也就是说，它对
*bidi-ordering 没有影响*：`<div dir="rtl">123,<wbr>456</div>` 展示 `123,456` 而不是 `456,123` （当不拆成两行的时候）。

出于相同原因，`<wbr>` 元素不会在换行的地方引入连字符。为了使连字符仅仅在行尾出现，使用**连字符软实体** (**`&shy;`**) 来代替。

这个元素首先在 Internet Explorer 5.5 中实现，并且在 HTML5 中官方定义。

## 示例

*Yahoo 代码规范* 推荐在标点之前为 URL 换行，以便避免将标点符号留在行尾（避免让读者将 URL 的末尾搞错）。

```html
<p>http://this<wbr>.is<wbr>.a<wbr>.really<wbr>.long<wbr>.example<wbr>.com/With<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages</p>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<wbr>` | 支持 | 支持 | 支持 |
