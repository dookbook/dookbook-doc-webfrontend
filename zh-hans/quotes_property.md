TOPICS: quotes property

# CSS 属性: `quotes`

CSS **`quotes`** 属性用于设置**引号的样式**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | [**`content`**](/zh-hans/webfrontend/content_property) 属性的值 *`open-quote`* 和 *`close-quote`* 将不会展示引号。|
| **"string" "string"** | 定义要**使用的引号**。<br>前两个值规定第一级引用嵌套，后两个值规定下一级引号嵌套。|

## 示例

```html
<q>To be or not to be. That's the question!</q>
```

```css
q {
  quotes: '"' '"' "'" "'";
}
q::before {
  content: open-quote;
}
q:after {
  content: close-quote;
}
```
