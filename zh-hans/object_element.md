TOPICS: <object>

# HTML 嵌入对象元素：`<object>`

**HTML 嵌入对象元素**（**`<object>`**）表示引入一个外部资源，这个资源可能是一张*图片* (使用 *`<img>`*)，一个*嵌入的浏览上下文*，亦或是一个*插件*所使用的资源。

## 属性

元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `form` | 对象元素关联的 form 元素（属于的 form）。 取值必须是同一文档下的一个 [`<form>`](/zh-hans/webfrontend/<form>) 元素的 ID。 |
| `height` | 资源显示的高度，单位是 CSS 像素。 |
| `name` | 浏览上下文名称（HTML5），或者控件名称（HTML 4）。 |
| `type` | **data** 指定的资源的 MIME 类型，需要为 **data** 和 **type** 中至少一个设置值。 |
| `usemap` | 指向一个 [`<map>`](/zh-hans/webfrontend/<map>) 元素的 hash-name；格式为 ‘#’ 加 map 元素 `name` 元素的值。 |
| `width` | 资源显示的宽度，单位是 CSS 像素。 |

## 示例

```html
<!-- Embed a flash movie -->
<object data="move.swf" type="application/x-shockwave-flash"></object>

<!-- Embed a flash movie with parameters -->
<object data="move.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
