TOPICS: :defined
AUTHORS: forever_youyou; foreveryouyou@github.com; github:foreveryouyou

# CSS 伪类: `:defined`

**`:defined`** CSS 伪类表示任何已定义的元素。这包括任何浏览器内置的标准元素以及已成功定义的自定义元素 (例如通过 `CustomElementRegistry.define()`方法)。

## 示例

在这个 demo 中我们定义了一个非常简单的自定义元素:

```javascript
customElements.define('simple-custom',
  class extends HTMLElement {
    constructor() {
      super();

      let divElem = document.createElement('div');
      divElem.textContent = this.getAttribute('text');

      let shadowRoot = this.attachShadow({mode: 'open'})
        .appendChild(divElem);
  }
})
```

然后在文档中插入一个该元素的副本，以及一个标准的 [`<p>`](/en/webfrontend/<p>) 标签:

```html
<simple-custom text="Custom element example text"></simple-custom>

<p>Standard paragraph example text</p>

```

在 CSS 中我们首先包含以下规则:

```css
// 为两个元素设置不同的背景色
p {
  background: yellow;
}

simple-custom {
  background: cyan;
}

// 将自定义元素和内置元素的字体都设为斜体
:defined {
  font-style: italic;
}
```

然后提供以下两个规则来隐藏未定义的自定义元素的所有实例，并显示被定义为块级元素的实例：

```css
simple-custom:not(:defined) {
  display: none;
}

simple-custom:defined {
  display: block;
}
```

这在你有一个复杂的自定义元素需要一段时间才能加载到页面中时非常有用 —— 你可能想要隐藏元素的实例直到定义完成为止，这样你就不会在页面上出现一些难看的元素。
