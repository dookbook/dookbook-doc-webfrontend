TOPICS: accesskey attribute

# HTML 全局属性: `accesskey`

**accesskey** [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) 提供了为当前元素**生成快捷键**的方式。属性值必须包含一个可打印字符。

!!! warn "注意"
    在WHATWG规范中，它说:你可以指定多个空格分隔的字符，但浏览器将使用它所支持的第一个字符。然而，这在大多数浏览器中是行不通的。但在IE/Edge中，它将使用它支持的第一个没有问题的，只要没有与其他命令冲突。

激活 accesskey 的操作取决于浏览器及其平台。

|  | Windows | Linux | Mac |
| :-- | :-- | :-- | :-- |
| **Firefox** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | 在Firefox 57或更高版本上： !!!Control!!! + !!!Option!!! + !!!key!!! or !!!Control!!! + !!!Alt!!! + !!!key!!!<br>在Firefox 14或更高版本上： !!!Control!!! + !!!Alt!!! + !!!key!!!<br>在Firefox 13或更高版本上：!!!Control!!! + !!!key!!! |
| **Edge** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Internet Explorer** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Google Chrome** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!!
| **Safari** | !!!Alt!!! + !!!key!!! | N/A | !!!Control!!! + !!!Alt!!! + !!!key!!! |
| **Opera 15+** | !!!Alt!!! + !!!key!!! | !!!Alt!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!! |
| **Opera 12** | !!!Shift!!! + !!!Esc!!! 打开一个accesskey可以访问的内容列表，然后按下key选择一个条目。| <- | <- |

要注意 Firefox 可以通过用户偏好，自定义所需的修饰键。

## 可访问性

除了糟糕的浏览器支持之外， `accesskey`属性还有很多问题：

- `accesskey` 值可能与系统或浏览器键盘快捷键或辅助技术功能相冲突。对于一个操作系统来说，辅助技术和浏览器组合可能无法与其他操作系统协同工作。
- 某些 `accesskey` 值可能不会出现在某些键盘上，特别是在国际化是一个问题的时候。
- 依赖于数字的 `accesskey` 值可能会使人感到困惑，因为他们的数字与它触发的功能没有逻辑关联。
- 通知用户 `accesskey` 存在，这样他们就能意识到该功能。如果没有公开这些信息的方法，`accesskey` 可能会被意外激活。

由于这些问题，一般建议不要在大多数通用的网站和web应用程序中使用 `accesskey` 属性。

- [WebAIM: Keyboard Accessibility - Accesskey](https://webaim.org/techniques/keyboard/accesskey#spec)
  
## 示例

```html
<a href="https://dookbook.info" accesskey="h">Dookbook</a><br />
<a href="//www.google.com/" accesskey="c">Google</a>

<p>
<b>注释：</b>
  请使用Alt + <i>accessKey</i> (或者 Shift + Alt + <i>accessKey</i>) 来访问带有指定快捷键的元素。
  </p>
```

带js案例：

```html
<script>
function accesskey(){
  document.getElementById('runoob').accessKey="r"
  document.getElementById('g').accessKey="g"
}
</script>
</head>
<body onload="accesskey()">
<a id="runoob" href="https://dookbook.info">Dookbook</a><br>
<a id="g" href="//www.google.com/">Google</a>
<p>
<b>注：</b>
使用Alt + <i> accesskey </i>访问具有指定快捷键的元素。
</p>
```

## 参见

- [`Element.accessKey`](/zh-hans/webfrontend/Element.accessKey)
- [`HTMLElement.accessKeyLabel`](/zh-hans/webfrontend/HTMLElement.accessKeyLabel)
- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。
