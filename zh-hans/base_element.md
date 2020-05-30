TOPICS: <base>
        <base> href attribute
        <base> target attribute

# HTML 文档根 URL 元素: `<base>`

**HTML `<base>` 元素** 指定用于一个文档中包含的所有相对 URL 的根 URL。一个文档中只能有一个 `<base>` 元素。

一个文档的基本 URL, 可以通过使用 `document.baseURI` 的 JS 脚本查询。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *元数据内容*。|
| **允许的内容** | 无，它是一个空元素。|
| **标签省略** | 该标签不能有结束标签。|
| **允许的父元素** | 任何不带有任何其他 `<base>` 元素的[`<head>`](/zh-hans/webfrontend/<head>) 元素。|
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLBaseElement`** |

## 属性

该标签包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`href`** | 用于文档中相对 URL 地址的基础 URL。如果指定了该属性，这个元素必须写在其他任何属性值是 URL 的元素之前。允许绝对和相对URL（但是请查看下面的注意节段）。 |
| **`target`** | 为没有显示target引用属性的元素指定一个名字或关键字，当元素的超链接或导致导航的形式被激活时，指定显示结果的默认位置。在HTML4中，其值是一个框的名字或者在关键字。在HTML5中，其值是一个浏览上下文（例如标签页，窗口或者内联框）的名字或者关键字。以下的关键字指定特殊的意思：<br>`_self`: 载入结果到当前的HTML4框（或者HTML5的浏览上下文）。如果没有指定该属性，那该值是元素的默认值属性值。<br>`_blank`: 载入结果到一个新的未命名HTML4窗口，或者一个新的HTML5的浏览上下文。<br>`_parent`: 对于HTML4，载入结果到当前框的父级框；对于HTML5，载入结果到父级浏览上下文。如果没有父级结构，该选项的行为和_self一样。<br>`_top`: 在HTML4中，载入结果到全部原始窗口，并且取消其他所有框。在HTML5中，载入结果到顶级浏览上下文（该浏览上下文是当前上下文的最顶级上下文）。如果没有父级，该选项的行为和_self一样。 |

## 使用说明

### 基本优先级

如果指定了多个 `<base>` 元素，只会使用第一个 `href` 和 `target` 值, 其余都会被忽略。

!!! warn "提示"
    请把`<base>`标签排在`<head>`元素中第一个元素的位置，这样`head`区域中其他元素就可以使用 `<base>` 元素中的信息了。

!!! warn "注释"
    如果使用了`<base>`标签，则必须具备`href`属性或者`target`属性或者两个属性都具备。

### 锚元素

`<a href="#anchor">anchor</a>`通过使用基本URL作为参考来解析页面内的锚点元素，并触发对基本URL的HTTP请求。

例如，以下给定基本URL：

```html
<base href="http://www.example.com/">
```

以及这个锚点:

```html
<a href="#anchor">Anker</a>
```

该链接指向:

`http://www.example.com/#anchor`

### Open Graph

Open Graph meta-TOPICS不认可基本URL，并且应始终具有完整URL。例如：

```html
<meta property='og:image' content='http://example.com/thumbnail.jpg'>
```

## 示例

```html
<base href="http://www.example.com/">
<base target="_blank" href="http://www.example.com/">
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<base>` | 支持 | 支持 | 支持 |
