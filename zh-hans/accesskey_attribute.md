TOPICS: accesskey attribute

# HTML 全局属性: `accesskey`

**accesskey** [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) 提供了为当前元素**生成快捷键**的方式。属性值必须包含一个可打印字符。

!!! warn "注意"
    在WHATWG规范中，它说你可以指定多个空格分隔的字符，浏览器将使用它所支持的第一个字符。然而，这在大多数浏览器中是行不通的。在IE/Edge中，它将使用它支持的第一个没有问题的，只要没有与其他命令冲突。

激活 accesskey 的操作取决于浏览器及其平台。

|  | Windows | Linux | Mac |
| :-- | :-- | :-- | :-- |
| **Firefox** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | On Firefox 57 or newer: !!!Control!!! + !!!Option!!! + !!!key!!! or !!!Control!!! + !!!Alt!!! + !!!key!!!<br>On Firefox 14 or newer: !!!Control!!! + !!!Alt!!! + !!!key!!!<br>On Firefox 13 or older: !!!Control!!! + !!!key!!! |
| **Edge** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Internet Explorer** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Google Chrome** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!!
| **Safari** | !!!Alt!!! + !!!key!!! | N/A | !!!Control!!! + !!!Alt!!! + !!!key!!! |
| **Opera 15+** | !!!Alt!!! + !!!key!!! | !!!Alt!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!! |
| **Opera 12** | !!!Shift!!! + !!!Esc!!! opens a contents list which are accessible by accesskey, then, can choose an item by pressing key | <- | <- |

要注意 Firefox 可以通过用户偏好，自定义所需的修饰键。

## 可访问性

除了糟糕的浏览器支持之外， `accesskey`属性还有很多问题：

- `accesskey` 值可能与系统或浏览器键盘快捷键或辅助技术功能相冲突。对于一个操作系统来说，辅助技术和浏览器组合可能无法与其他操作系统协同工作。
- 某些 `accesskey` 值可能不会出现在某些键盘上，特别是在国际化是一个问题的时候。
- 依赖于数字的 `accesskey` 值可能会让那些经历认知问题的人感到困惑，因为他们的数字与它触发的功能没有逻辑关联。
- 通知用户 `accesskey` 存在，这样他们就能意识到该功能。如果没有公开这些信息的方法，`accesskey` 可能会被意外激活。

由于这些问题，一般建议不要在大多数通用的网站和web应用程序中使用 `accesskey` 属性。

- [WebAIM: Keyboard Accessibility - Accesskey](https://webaim.org/techniques/keyboard/accesskey#spec)

## 参见

- [`Element.accessKey`](/zh-hans/webfrontend/Element.accessKey)
- [`HTMLElement.accessKeyLabel`](/zh-hans/webfrontend/HTMLElement.accessKeyLabel)
- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
