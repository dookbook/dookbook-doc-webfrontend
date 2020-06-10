TOPICS: <map>
        <area>
        <map> name attribute
        <area> href attribute
        <area> shape attribute
        <area> coords attribute
        <area> coords attribute
        <area> target attribute
        <area> rel attribute
        <area> download attribute
        <area> type attribute
        <area> hreflang attribute
        <area> ping attribute

# HTML图像映射：`<map>`和`<area>`

**HTML`<map>`元素** 与 **`<area>`元素**一起使用来定义一个**图像映射**(一个*可点击的链接区域*)。

**HTML`<area>`元素**在图片上定义一个**热点区域**（即在图片上指定一个鼠标可点击的链接区域），可以关联一个**超链接**。`<area>`元素仅在 *`<map>`* 元素内部使用。

## 技术摘要

|  | `<map>` |`<area>`|
| :-- | :-- |:-- |
| **内容类别** | *流式内容*，*短语内容*，*可触摸内容*。| *流式内容*, *短语内容* |
| **允许的内容** | 任何*透明*元素。| 无，它是一个 **[空元素](/zh-hans/webfrontend/empty_element)**。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。| 不允许，只能允许有开始标签不允许有结束标签。|
| **允许的父元素** | 任何允许 *短语内容* 的元素。| `<area>` 元素必须拥有一个 `<map>` 元素祖先元素，但不一定是直接的父元素。|
| **DOM 接口** | **`HTMLMapElement`** | **`HTMLAreaElement`** |

## `<map>`属性

这个元素拥有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`name`** | 给图像映射一个名字用来引用。这个属性是**必需的**，值不能为空并且**不能带空格**。<br>`name`属性不允许与同文档中其他`<map>`元素的`name`属性值相同。**如果存在 *`id`* 属性，则`name`属性和`id`属性的值必须相同。** |

## `<area>`属性

| 属性 | 描述 |
| :-- | :-- |
| **`href`** | 指定**映射区域的超链接**。它的值为一个[[URL]]。HTML 4这个值不管是不是有值都要明确指定出来，HTML 5 则不需要。|
| **`alt`** | 在未显示图像的浏览器上显示**代替的文本字符串**。这个文本应该能传达给用户与显示图像在没有文本的情况下可以做出同样的选择（译者注：就是字和图片表达一个意思）。在HTML 4中， 这个属性时必需的,但是可以是一个空的串(`""`)。在 HTML 5中, 这个属性只有在 *`href`* 属性被使用的时候才是必需的。|
| **`shape`** | 指定**映射的热点区域的形状**。|
| **`coords`** | 给热点区域设定具体的**坐标值**。这个值的数值和意义取决于这个值所描述的 *`shape`*属性。|
| `target` | 此属性指明了在**什么地方显示链接的资源**。请查看 *[`<a>`](/zh-hans/webfrontend/<a>)* 获得关于`target`属性的完整描述。|
| `rel` | 对于包含*`href`*属性的锚，该属性指定**目标对象与链接对象的关系**。请查看 *[`<a>`](/zh-hans/webfrontend/<a>)* 获得关于`rel`属性的完整描述。|
| `download` | 这个属性如果存在的话, 表明作者想把超链接用于**下载一个资源**。请查看 *[`<a>`](/zh-hans/webfrontend/<a>)* 获得关于`download`属性的完整描述。 |
| `type` | 该属性指定了用于**链接目标的[[MIME]]类型的媒体类型**。用法同 *[`<a>`](/zh-hans/webfrontend/<a>)* 的`type`属性。|
| `hreflang` | 指明**链接资源的语言类型**。请查看 *[`<a>`](/zh-hans/webfrontend/<a>)* 获得关于`hreflang`属性的完整描述。 |
| `ping` | 包含一个以空格分隔的URL列表，当跟随超链接时，将由浏览器(在后台)发送带有正文 PING的`POST`请求。通常用于**跟踪**。用法同 *[`<a>`](/zh-hans/webfrontend/<a>)* 的`ping`属性。 |
| `referrerpolicy` | 一个字符串，指在获取资源时使用哪个引荐来源网址：<br>`"no-referrer"` 表示`Referer`: 不会发送标头。<br>`"no-referrer-when-downgrade"` 表示`Referer`在导航到没有TLS（HTTPS）的来源时不会发送任何标头。如果未指定其他方式是，这是用户代理为默认模式。<br>`"origin"` 表示引荐来源网址将是来源页面，大致是方案、主机和端口。<br>`"origin-when-cross-origin"` 表示到其他来源的导航将仅限于方案，主机和端口，而在同一来源的导航将包括引荐来源网址的路径。 <br>`"unsafe-url"` 意味着引荐来源网址将包含来源和路径（但不包括片段，密码或用户名）。这种情况是不安全的，因为它可能会将来源和路径从受TLS保护的资源泄漏到不安全的来源。|
| ~~`name`~~ | **已废弃**。为可点击区域定义一个名字以使旧浏览器解析。 |
| ~~`nohref`~~ | **已废弃**。指明此区域没有超链接。 |
| ~~`tabindex`~~ | **已废弃**。用于指定浏览器tab键获取焦点的顺序。 |

## `shape`和`coords`属性值

| `shape`属性值 | 描述 | 规范 | `shape`属性值 |
| :--: | :-- | :--: | :--: |
| **`rect`** | *矩形*区域 | HTML4, HTML5 | 两个`x,y`对：*左上*、*右下* |
| **`circle`** | *圆形*区域 | HTML4, HTML5 | `x,y,r`，这里的`x,y`是圆心的坐标，而`r`则表示的是半径值。|
| **`poly`** | *多边形* | HTML4, HTML5 | 用`x,y`对表示的多边形的每一个点：`x1,y1,x2,y2,x3,y3,`等等 |
| **`default`** | 默认情况下，整个区域 | HTML4, HTML5 |

HTML4中，*`coords`*值可能是像素值或者百分比, 区别是不是有`%`出现; HTML5里, 只可能是*像素值*。

## 图像映射的示例

```html
<img src="url" alt="replacement text" title="hint text" usemap="#map-id">
<map id="map-id">
  <area shape="rect"
        coords="leftTop-x,leftTop-y,rightBottom-x,rightBottom-y"
        alt="replacement text 1" title="hint text 1" href="url-1">
  <area shape="circle"
        coords="center-x,center-y,radius"
        alt="replacement text 2" title="hint text 2" href="url-2">
  <area shape="circle" coords="center-x2,center-y2,radius2">
</map>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<map>` | 支持 | 支持 | 支持 |
| `<area>` | 支持 | 支持 | 支持 |
