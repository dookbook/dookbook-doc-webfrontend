TOPICS: <param>

# `<param>`

HTML `<param>`元素为[`<object>`](/zh-hans/webfrontend/<object>)元素定义参数。

`<param>` 标签支持大部分主流浏览器。但是[`<object>`](/zh-hans/webfrontend/<object>)定义的文件格式不是所有的浏览器都支持。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | 无 |
| **允许内容** | 不允许，它是一个空元素（empty element）。|
| **标签省略** | 由于它是一个void元素，所以开始标签必须出现，而结束标签必须不出现。|
| **允许的父元素** | 任何以下内容（*流式内容*）(url）都可以在[`<object>`](/zh-hans/webfrontend/<object>)元素的前面作为它的父元素。|
| **DOM 接口** | **`HTMLParamElement`** |

## 属性

这个元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `name` | 参数的名字 |
| `value` | 确定参数的值。 |
| `type` | **HTML5不支持**。定义 MIME 类型参数。|
| `valuetype` | **HTML5 不支持**。描述值的类型。|

## 示例

```html
<!-- 嵌入带有参数的Flash电影 -->
<object data="move.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<param>`  | 支持 | 支持 | 支持 |
