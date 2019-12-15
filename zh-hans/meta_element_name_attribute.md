TOPICS: <meta> name attribute

# `<meta>`元素的`name`属性

该属性定义了一段文档级**元数据的名称**。如果还设置了属性`itemprop`，[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)或[`charset`](/zh-hans/webfrontend/<meta>_charset_attribute)之一，则不应设置此属性。

此元数据名称与`content`属性所包含的值相关。

## `<meta name="application-name">`

**`application-name`**，用于定义在网页中运行的**应用程序的名称**。

**注意：** 浏览器可以使用它来标识该应用程序。它与通常包含应用程序名称的[`<title>`](/zh-hans/webfrontend/<title>)元素不同，但也可能包含文档名称或状态之类的信息。

简单的网页不应定义应用程序名称`application-name`。

## `<meta name="author">`

**`author`**，用于定义文档的**作者信息**。

例如：

```html
<!-- 标注网站作者信息：Dookbook是这个网页的作者 -->
<meta name="author" content="Dookbook">
```

## `<meta name="description">`

**`description`**，用于包含页面内容的**简短准确摘要**。一些浏览器，例如Firefox和Opera，都将其用作添加了书签的页面的默认描述。

例如：

```html
<!-- 描述这个网页 -->
<meta name="description" content="A Dookbook webpage">
```

## `<meta name="generator">`

**`generator`**，用于包含生成页面的**软件的标识符**。

## `<meta name="keywords">`

**`keywords`**，用于包含与**页面内容相关的单词**，用*逗号*隔开。

例如：

```html
<!-- 关于这个网页的关键字，用逗号隔开 -->
<meta name="keywords" content="Dookbook,a,b">
```

## `<meta name="referrer">`

**`referrer`**，用于控制附加到文档发送的请求的`Referer`HTTP头部。

### `<meta name="referrer">`的`content`属性值

!!! warn "注意"
    - 某些浏览器支持废弃的`referrer`值：`always`，`default`和`never`。
    - 动态插入`<meta name =“ referrer”>`（带有`document.write`或`appendChild`）会使引荐来源网址的行为不可预测。
    - 当定义了多个冲突策略时，将应用无引用策略`no-referrer`。

| 值 | 描述 |
| :-- | :-- |
| `no-referrer` | 不发送HTTP `Referer`头部. |
| `origin` | 发送文件来源. |
| `no-referrer-when-downgrade` | 将来源作为引荐来源发送到与当前页面一样安全的URL（https→https），但不将引荐来源发送给安全程度较低的URL（https→http）。 这是*默认*行为.|
| `origin-when-cross-origin` | 发送相同来源请求的完整URL（带参数的），但仅发送其他情况下的来源. |
| `same-origin` | 将发送针对相同站点来源的引荐来源网址，但跨域请求将不包含引荐来源网址信息. |
| `strict-origin` | 仅将文档的原始来源作为引荐来源发送到优先级较高的目标（HTTPS-> HTTPS），而不将其发送到安全性较低的目标（HTTPS-> HTTP）. |
| `strict-origin-when-cross-origin` | 在执行相同来源的请求时发送完整的URL，仅将文档的原点发送到先验的非常安全的目标（HTTPS-> HTTPS），不发送标头到次安全的目标（HTTPS-> HTTP ）. |
| `unsafe-URL` | 发送同源或跨域请求的完整URL（带参数的URL）. |