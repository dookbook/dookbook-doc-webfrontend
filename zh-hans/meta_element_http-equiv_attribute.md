TOPICS: <meta> http-equiv attribute  <!-- markdownlint-disable proper-names -->
<!-- markdownlint-enable proper-names -->

# `<meta>`元素的`http-equiv`属性

定义一个**编译指示**。该属性被命名为"*`http-equiv`(alent)*"，因为所有允许的值都是特定**HTTP头部**的名称。

## `content-language`

!!! error "已过时废弃"
    请改用[`<html>`](/zh-hans/webfrontend/<html>)元素上的`lang`属性替代。

## `content-security-policy`

允许定义当前页面的**内容策略**。内容策略主要指定允许的服务器来源和脚本端点，以帮助防止跨站点脚本攻击。

## `content-type`

!!! error "已过时废弃"
    请改用[`<meta>`](/zh-hans/webfrontend/<meta>)元素上的`charset`属性来替代。

## `refresh`

此指令指定：

1. **重新加载当前页面的间隔时间（单位：秒）** - 仅在`content`属性包含*正整数*的情况下。
2. **重定向到另一页面的时间间隔**（单位：秒) - 仅在`content`属性包含*正整数*后跟字符串 `;url=`和有效URL的情况下。

"`refresh`" 应该慎重使用，因为它会使得页面不受用户控制。在 [W3C's Web 内容可访问性指南中](http://www.w3.org/WAI/intro/wcag.php) 使用
"`refresh`" 会到导致失败。

### 刷新内容示例

```html
<!-- 3秒后重新加载（刷新）这个网页 -->
<meta http-equiv="refresh" content="3">
<meta http-equiv="refresh" content="3;url=https://dookbook.info">
```

### 刷新内容的可访问性问题

设置了刷新值的页面存在时间间隔太短的风险。借助屏幕阅读器等辅助技术进行导航的人们在自动重定向之前可能无法阅读并理解页面的内容。页面内容的突然且未经通知的更新也可能使视力低下的人迷失方向。

- [MDN了解WCAG，准则2.1的说明](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#Guideline_2.2_%E2%80%94_Enough_Time_Provide_users_enough_time_to_read_and_use_content)
- [MDN了解WCAG，准则3.1的说明](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#Guideline_3.2_%E2%80%94_Predictable_Make_Web_pages_appear_and_operate_in_predictable_ways)
- [了解成功标准2.2.1 | W3C了解WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-required-behaviors.html)
- [了解成功标准2.2.4 | W3C了解WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-postponed.html)
- [了解成功标准3.2.5 | W3C了解WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/consistent-behavior-no-extreme-changes-context.html)

## `default-style`

规定要使用的预定义的样式表。

```html
<meta http-equiv="default-style" content="the document's preferred stylesheet">
```

**注意**：示例中`content`属性的值必须匹配同一文档中的一个[`link`](/zh-hans/webfrontend/<link>)元素上的 `title`属性的值，或者必须匹配同一文档中的一个[`style`](/zh-hans/webfrontend/<style>)元素上的`title`属性的值。

## `set-cookie`

!!! error "已过时废弃"
    请改用HTTP标头`Set-Cookie`来替代。

## `X-UA-Compatible`

要求浏览器采取何种版本渲染当前页面。

```html
<!-- 最新版本的IE和Chrome -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
```
