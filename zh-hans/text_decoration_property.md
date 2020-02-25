TOPICS: text-decoration property

# CSS 属性: `text-decoration`

**`text-decoration`** CSS 属性是用于设置**文本排版（下划线、顶划线、删除线或者闪烁）**。

文本修饰属性会延伸到子元素。这意味着如果祖先元素指定了文本修饰属性，子元素则不能将其删除。例如，在如下标记中
`<p>This text has <em>some emphasized words</em> in it.</p>`，应用样式`p { text-decoration: underline }`
会对整个段落添加下划线，此时再添加样式 `em { text-decoration: none }` 则不会引起任何改变，整个段落仍然有下划线修饰。然而，新加样式
`em { text-decoration: overline }` 则会在 [`<em>`](/zh-hans/webfrontend/<em>) 标记的文字上再添加上这种`overline`样式。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 默认。标准的文本。|
| **`underline`** | 文本下的一条线。|
| **`overline`** | 文本上的一条线。|
| **`line-through`** | 穿过文本下的一条线。|

## 示例

```css
h1 {text-decoration: overline;}
h2 {text-decoration: line-through;}
h3 {text-decoration: underline;}
```

```html
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
```
