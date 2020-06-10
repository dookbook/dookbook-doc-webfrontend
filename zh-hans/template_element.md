TOPICS: <template>

# `<template>`

**HTML内容模板 `<template>` 元素**是一种用于保存客户端内容机制，该内容在加载页面时不会呈现，但随后可以在运行时使用JavaScript实例化。

将模板视为一个内容片段，存储在文档中供后续使用。虽然解析器在加载页面时确实会处理 **`<template>`** 元素的内容，但这样做只是为了确保这些内容有效；然而，元素的内容不会被呈现。

## 属性

此元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 示例

首先我们从示例的HTML部分开始。

```html
<table id="producttable">
  <thead>
    <tr>
      <td>UPC_Code</td>
      <td>Product_Name</td>
    </tr>
  </thead>
  <tbody>
    <!-- 现有数据可以可选地包括在这里 -->
  </tbody>
</table>

<template id="productrow">
  <tr>
    <td class="record"></td>
    <td></td>
  </tr>
</template>
```

首先，我们有一个表，稍后我们将使用JavaScript代码在其中插入内容。然后是模板，它描述了表示单个表行的HTML片段的结构。

既然已经创建了表并定义了模板，我们使用JavaScript将行插入到表中，每一行都是以模板为基础构建的。

```javascript
// 通过检查来测试浏览器是否支持HTML模板元素
// 用于保存模板元素的内容属性。
if ('content' in document.createElement('template')) {

  // 使用现有的HTML tbody实例化表和该行与模板
  let t = document.querySelector('#productrow'),
  td = t.content.querySelectorAll("td");
  td0].textContent = "1235646565";
  td1].textContent = "Stuff";

  // 克隆新行并将其插入表中
  let tb = document.getElementsByTagName("tbody");
  let clone = document.importNode(t.content, true);
  tb0].appendChild(clone);
  
  // 创建一个新行
  td0].textContent = "0384928528";
  td1].textContent = "Acme Kidney Beans";

  // 克隆新行并将其插入表中
  let clone2 = document.importNode(t.content, true);
  tb0].appendChild(clone2);

} else {
  // 找到另一种方法来添加行到表，因为不支持HTML模板元素。
}
```

结果是原始的HTML表格，通过JavaScript添加了两行新内容：

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<template>` | 支持 | 支持 | 支持 |
