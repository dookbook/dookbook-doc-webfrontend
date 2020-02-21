TOPICS: :host()

# CSS 伪类: `:host()`

**`:host()`** CSS伪类函数选择包含其内部使用的CSS的**影子DOM**的**影子宿主**（因此您可以从其影子DOM内部选择自定义元素），但前提是作为函数参数给出的选择器与影子主机匹配。

最明显的用途是仅在某些自定义元素实例上放置一个类名，然后将相关的类选择器作为函数参数包含在内。您不能将其与后代选择器表达式一起使用来仅选择特定祖先内的自定义元素的实例，这就是`:host-context()`的工作。

!!! warn "注意"
    在影子DOM外部使用时，这无效。

## 语法

```css
/* 选择影子根主机，仅当它是
    与选择器参数匹配 */
:host(.special-custom-element) {
  font-weight: bold;
}
```

## 示例

以下摘录摘自我们的主机选择器示例（另请参见实况）。

在此示例中，我们有一个简单的自定义元素— `<context-span>`，您可以在其周围包裹文本：

```html
<h1>Host selectors <a href="#"><context-span>example</context-span></a></h1>
```

在元素的构造函数中，我们创建`style`和`span`元素，用自定义元素的内容填充`span`，并用一些CSS规则填充`style`元素：

```javascript
let style = document.createElement('style');
let span = document.createElement('span');
span.textContent = this.textContent;

const shadowRoot = this.attachShadow({mode: 'open'});
shadowRoot.appendChild(style);
shadowRoot.appendChild(span);

style.textContent = 'span:hover { text-decoration: underline; }' +
                    ':host-context(h1) { font-style: italic; }' +
                    ':host-context(h1):after { content: " - no links in headers!" }' +
                    ':host-context(article, aside) { color: gray; }' +
                    ':host(.footer) { color : red; }' +
                    ':host { background: rgba(0,0,0,0.1); padding: 2px 5px; }';
```

`:host(.footer){颜色:红色;}`样式设置文档中所有设置了`footer`类的元素`<context-span>`元素的所有实例（在此实例中为影子主机）–我们已使用它为元素提供了实例 `<footer>`是一种特殊的颜色。
