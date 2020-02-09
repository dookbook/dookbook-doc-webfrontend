TOPICS: dir attribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# HTML 全局属性: `dir`

!!! warn "注意“
    在 HTML 4.01 中，~~`<dir>`~~元素已废弃。 但在 HTML5 中,`dir`属性可用于任何的HTML元素(它会验证任何HTML元素。但不一定是有用)。在 HTML 4.01
    中, `dir` 元素不能用于: `<base>`, `<br>`, `<frame>`, `<frameset>`, `<hr>`,`<iframe>`, `<param>`, 和 `<script>`。

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)**`dir`**是一个指示元素中文本方向的枚举属性。它的取值如下：

- `ltr`, 指从左到右，用于那种从左向右书写的语言（比如英语）；
- `rtl`, 指从右到左，用于那种从右向左书写的语言（比如阿拉伯语）；
- `auto`, 指由用户代理决定方向。它在解析元素中字符时会运用一个基本算法，直到发现一个具有强方向性的字符，然后将这一方向应用于整个元素。

!!! warn "Don't try this at home"
    使用说明:
    这个属性对有不同语义的[`<bdo>`](/zh-hans/webfrontend/<bdo>)元素是必须的。
    这个属性在[`<bdi>`](/zh-hans/webfrontend/<bdi>)元素中不可继承。未赋值时，它的默认值是auto。
    这个属性可以被CSS属性[`direction`](/zh-hans/webfrontend/direction)和[`unicode-bidi`](/zh-hans/webfrontend/unicode-bidi)覆盖，如果CSS网页有效且该元素支持这些属性的话。
    由于文本的方向是和内容的语义而不是和表现相关，因此有可能的话，网页开发者使用这一属性而非CSS属性是被推荐的。这样，即使在不支持CSS或禁用CSS的浏览器中，文本也会正常显示。
    auto应当用于方向未知的数据，如用户输入的数据，最终保存在数据库中的数据。

## 可访问性

除了糟糕的浏览器支持之外， `accesskey`属性还有很多问题：

- `accesskey` 值可能与系统或浏览器键盘快捷键或辅助技术功能相冲突。对于一个操作系统来说，辅助技术和浏览器组合可能无法与其他操作系统协同工作。
- 某些 `accesskey` 值可能不会出现在某些键盘上，特别是在国际化是一个问题的时候。
- 依赖于数字的 `accesskey` 值可能会让那些经历认知问题的人感到困惑，因为他们的数字与它触发的功能没有逻辑关联。
- 通知用户 `accesskeys` 存在，这样他们就能意识到该功能。如果没有公开这些信息的方法，`accesskeys` 可能会被意外激活。

由于这些问题，一般建议不要在大多数通用的网站和web应用程序中使用 `accesskey` 属性。

- [WebAIM: Keyboard Accessibility - Accesskey](https://webaim.org/techniques/keyboard/accesskey#spec)

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- 对应这个属性的[`HTMLElement.dir`](/zh-hans/webfrontend/HTMLElement.dir)。
