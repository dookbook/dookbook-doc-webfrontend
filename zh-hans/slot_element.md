TOPICS: <slot>

# `<slot>`

**HTML `<slot>` 元素** —是 Web Components 技术套件的一部分，是Web组件内的一个占位符，可以使用自己的标记填充，这样您就可以创建单独的DOM树并将它们组合在一起。

## 属性

此元素有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `name` | 插槽的名字 |

拥有name属性的插槽叫**具名插槽** 。

## 示例

```html
<template id="element-details-template">
<style>
details { font-family: "Open Sans Light", Helvetica, Arial, sans-serif; }

.name {
  font-weight: bold;
  color: #217ac0;
  font-size: 120%;
}

h4 {
  margin: 10px 0 -8px 0;
  background: #217ac0;
  color: white;
  padding: 2px 6px;
  border: 1px solid #cee9f9;
  border-radius: 4px;
}

.attributes {
  margin-left: 22px;
  font-size: 90%;
}

.attributes p {
  margin-left: 16px;
  font-style: italic;
}
</style>
  <details>
    <summary>
      <code class="name">&lt;<slot name="element-name">NEED NAME</slot>&gt;</code>
      <i class="desc"><slot name="description">NEED DESCRIPTION</slot></i>
    </summary>
    <div class="attributes">
      <h4>Attributes</h4>
      <slot name="attributes"><p>None</p></slot>
    </div>
  </details>
  <hr>
</template>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<slot>` | 支持 | 支持 | 支持 |
