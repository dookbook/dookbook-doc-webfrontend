TOPICS: <object>

# HTML 嵌入对象元素：`<object>`

**HTML 嵌入对象元素**（**`<object>`**）表示引入一个外部资源，这个资源可能是一张*图片* (使用 *[`img`](/zh-hans/webfrontend/<img>)*)，
*音频*、*视频*、*`Java applets`*、*`ActiveX`*、*PDF*以及 *Flash*。

`object`的初衷是取代 [`img`](/zh-hans/webfrontend/<img>) 和 [`applet`](/zh-hans/webfrontend/<applet>) 元素。不过由于漏洞以及缺乏浏览器支持，这一点并**未实现**。

浏览器的对象支持赖于*对象类型*。不幸的是，主流浏览器都使用不同的代码来加载相同的对象类型。
而幸运的是，`object` 对象提供了解决方案。如果未显示`object`元素，就会执行位于 `<object>` 和 `</object>` 之间的代码。通过这种方式，我们能够*嵌套多个`object`元素（每个对应一个浏览器）*。

## 属性

元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `data` | 一个合法的URL作为资源的地址，需要为 **`data` 和 `type` 中至少一个设置值**。|
| `form` | 对象元素关联的`form`元素（属于的`form`）。 取值必须是同一文档下的一个 [`<form>`](/zh-hans/webfrontend/<form>) 元素的 ID。 |
| `height` | 资源显示的高度，单位是 CSS 像素。 |
| `name` | 浏览上下文名称（HTML5），或者控件名称（HTML 4）。 |
| `type` | **`data`** 指定的资源的 MIME 类型，需要为 **`data`** 和 **`type`** 中至少一个设置值。 |
| `usemap` | 指向一个 [`<map>`](/zh-hans/webfrontend/<map>) 元素的 `hash-name`；格式为 ‘#’ 加 `map` 元素 `name` 元素的值。 |
| `width` | 资源显示的宽度，单位是 CSS 像素。 |

### 废弃属性

| 属性 | 描述 |
| :-- | :-- |
| ~~`archive`~~ | **已废弃**，用来指名对象资源列表的以空格分隔的URI列表。 |
| ~~`border`~~ | **已废弃**，元素周围的边框的宽度，单位为像素。 |
| ~~`classid`~~ | **已废弃**，对象实现的 URI，可以同时与`data`属性使用，或者**使用`data`属性替代**。|
| ~~`codebase`~~ | **已废弃**，解析 `classid`，`data`或者 `archive` 中定义的相对路径的根路径，如果没有定义，默认为当前文档的 `base` URI。 |
| ~~`codetype`~~ | **已废弃**，`classid` 定义的`data`的内容类型。 |
| ~~`declare`~~ | **已废弃**，取值为布尔的属性可以设置这个元素仅为声明的格式。 |
| ~~`standby`~~ | **已废弃**，对象的实现和数据加载过程中，浏览器可以显示的信息。 |
| ~~`tabindex`~~ | **已废弃**，当前元素在文档 Tab 导航中的顺序。 |

## 示例

```html
<!-- Embed a flash movie -->
<object data="move.swf" type="application/x-shockwave-flash"></object>

<!-- Embed a flash movie with parameters -->
<object data="move.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
