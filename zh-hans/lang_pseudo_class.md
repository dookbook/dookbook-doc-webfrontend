TOPICS: :lang()
AUTHORS: 石博文; http_wenwen@live.com; github:Ritr
         ShirelyGong; ShirelyGong@github.com; github:ShirelyGong
         King; King.@mozilla.net; mdn:King.
         DongyaGe; DongyaGe@github.com; github:DongyaGe

# CSS 伪类: `:lang()`

**`:lang()`** CSS 伪类基于元素语言来匹配页面元素。

!!! warn "注意"
    在HTML中, 语言是通过 `lang` 属性，和[`<meta>`](/zh-hans/webfrontend/<meta>) 元素的组合来决定的，也可能是通过协议的信息来确定（例如HTTP头）。对于其他文档类型，也可能存在其他用于确定语言的方法。

## 示例

在这个例子中, `:lang()` 伪类使用子选择器来匹配引用元素([`<q>`](/zh-hans/webfrontend/<q>))的父元素. 需要注意的是，此处演示的方法并不是唯一的，
最好的方法需要依据文档类型来确定。还需要注意的是，Unicode 值用于指定一些特殊字符的引用.

```html
<div lang="en"><q>This English quote has a <q>nested</q> quote inside.</q></div>
<div lang="fr"><q>This French quote has a <q>nested</q> quote inside.</q></div>
<div lang="de"><q>This German quote has a <q>nested</q> quote inside.</q></div>
```

```css
:lang(en) > q { quotes: '\201C' '\201D' '\2018' '\2019'; }
:lang(fr) > q { quotes: '« ' ' »'; }
:lang(de) > q { quotes: '»' '«' '\2039' '\203A'; }
```
