TOPICS: Document.querySelector
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.querySelector()`

文档对象模型`Document`引用的`querySelector()`方法返回文档中与指定选择器或选择器组匹配的第一个 HTML元素`Element`。 如果找不到匹配项，则返回`null`。

!!! warn "提示"
    匹配是使用深度优先先序遍历，从文档标记中的第一个元素开始，并按子节点的顺序依次遍历。

## 语法

```javascript
element = document.querySelector(selectors);
```

| 参数 | 说明 |
| :-- | :-- |
| `selectors` | 包含一个或多个要匹配的选择器的 DOM字符串`DOMString`。 该字符串必须是有效的CSS选择器字符串；如果不是，则引发`SYNTAX_ERR`异常。请参阅使用选择器定位DOM元素以获取有关选择器以及如何管理它们的更多信息。 |

!!! warn "提示"
    必须使用反斜杠字符转义不属于标准CSS语法的字符。 由于JavaScript也使用退格转义，因此在使用这些字符编写字符串文字时必须特别小心。

**返回值**: 表示文档中与指定的一组CSS选择器匹配的第一个元素的 HTML元素`Element`对象。

如果您需要与指定选择器匹配的所有元素的列表，则应该使用`querySelectorAll()`。

## 异常

|  |  |
| :-- | :-- |
| `SYNTAX_ERR` | 指定`selectors`的语法无效。|

## 注意

如果选择器是一个 ID，并且这个 ID 在文档中错误地使用了多次，那么返回第一个匹配该 ID 的元素。

CSS 伪类不会返回任何元素，见 Selectors API 中的相关规定。

### 转义特殊字符

如果要匹配的ID或选择器不符合 CSS 语法（比如不恰当地使用了冒号或者空格），你必须用反斜杠将这些字符转义。由于 JavaScript 中，反斜杠是转义字符，所以当你输入一个文本串时，
你必须将它转义两次（一次是为 JavaScript 字符串转义，另一次是为 querySelector 转义）：

```html
<div id="foo\bar"></div>
<div id="foo:bar"></div>

<script>
  console.log('#foo\bar')               // "#fooar"
  document.querySelector('#foo\bar')    // 不匹配任何元素

  console.log('#foo\\bar')              // "#foo\bar"
  console.log('#foo\\\\bar')            // "#foo\\bar"
  document.querySelector('#foo\\\\bar') // 匹配第一个div

  document.querySelector('#foo:bar')    // 不匹配任何元素
  document.querySelector('#foo\\:bar')  // 匹配第二个div
</script>
```

## 查找第一个匹配 class属性的HTML元素

这个例子中，会返回当前文档中第一个类名为 `"myclass"` 的元素：

```javascript
var el = document.querySelector(".myclass");
```

## 一个更复杂的选择器

选择器也可以非常强大，如以下示例所示.

这里, 一个class属性为"user-panel main"的div元素`<div>`(`<div class="user-panel main">`)内包含一个name属性为
"login"的input元素`<input>` (`<input name="login"/>`) ，如何选择，如下所示:

```javascript
var el = document.querySelector("div.user-panel.main input[name='login']");
```
