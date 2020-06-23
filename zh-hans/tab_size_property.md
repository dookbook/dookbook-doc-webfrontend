TOPICS: tab-size property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `tab-size`

CSS 属性 **`tab-size`** 用于自定义制表符 (U+0009) 的**宽度**。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **number** | 默认值是 `8`。规定每个制表符（tab）字符要显示的空格字符的数量。 |
| **length** | 规定制表符（tab）字符的长度。几乎所有的主流浏览器都不支持该属性值。 |

## 示例

```css
#t1{
  tab-size: 4;
}

#t2{
  tab-size: 16;
}
```

```html
<pre id="t1">
I use tab-size 4
</pre>

<pre id="t2">
I use tab-size 16
</pre>
```
