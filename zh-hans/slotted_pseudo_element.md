TOPICS: ::slotted()
AUTHORS: LoveofRedMoon; LoveofRedMoon@github.com; github:LoveofRedMoon

# CSS 伪元素: `::slotted()`

**`:slotted()`** CSS 伪元素用于**选定那些被放在 HTML模板 中的元素**。

这个伪类选择器仅仅适用于 *影子节点树*(Shadow DOM). 并且只会选择实际的元素节点，而不包括文本节点.

## 示例

下面的小片段是关于 插槽伪类元素小demo.

在这个小demo 中, 我们使用一个带有3个插槽的HTML模板:

```html
<template id="person-template">
  <div>
    <h2>Personal ID Card</h2>
    <slot name="person-name">NAME MISSING</slot>
    <ul>
      <li><slot name="person-age">AGE MISSING</slot></li>
      <li><slot name="person-occupation">OCCUPATION MISSING</slot></li>
    </ul>
  </div>
</template>
```

自定义元素 `<person-details>` 的定义如下:

```javascript
customElements.define('person-details',
  class extends HTMLElement {
    constructor() {
      super();
      let template = document.getElementById('person-template');
      let templateContent = template.content;

      const shadowRoot = this.attachShadow({mode: 'open'});

      let style = document.createElement('style');
      style.textContent = 'div { padding: 10px; border: 1px solid gray; width: 200px; margin: 10px; }' +
                           'h2 { margin: 0 0 10px; }' +
                           'ul { margin: 0; }' +
                           'p { margin: 10px 0; }' +
                           '::slotted(*) { color: gray; font-family: sans-serif; } ';

      shadowRoot.appendChild(style);
      shadowRoot.appendChild(templateContent.cloneNode(true));
  }
})
```

为了更好地区分 **未被成功填充的插槽和成功填充的插槽**, 我们在CSS中选择了所有的插槽元素(`::slotted(*)`), 并填充了不一样的颜色和字体. 结果也是如此.

元素就像如下被填充了起来:

```html
<person-details>
  <p slot="person-name">Dr. Shazaam</p>
  <span slot="person-age">Immortal</span>
  <span slot="person-occupation">Superhero</span>
</person-details>
```
