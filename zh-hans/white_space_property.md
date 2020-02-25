TOPICS: white-space property

# CSS 属性: `white-space`

**`white-space`** CSS 属性是用来设置**如何处理元素中的空白**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 连续的空白符会被合并，换行符会被当作空白符来处理。填充行列盒子时，必要的话会换行。|
| **`nowrap`** | 和 `normal` 一样，连续的空白符会被合并。但文本内的换行无效。|
| **`pre`** | 连续的空白符会被保留。在遇到换行符或者[`<br>`](/zh-hans/webfrontend/<br>)元素时才会换行。|
| **`pre-wrap`** | 连续的空白符会被保留。在遇到换行符或者[`<br>`](/zh-hans/webfrontend/<br>)元素，或者需要为了填充行列盒子时才会换行。|
| **`pre-line`** | 连续的空白符会被合并。在遇到换行符或者[`<br>`](/zh-hans/webfrontend/<br>)元素，或者需要为了填充行列盒子时会换行。|

下面的表格总结了各种 `white-space` 值的行为：

| - | 换行符 | 空格和制表符 | 文字转行 | 行尾空格 |
| :--- | --- | --- | --- | --- |
| `normal` | 合并 | 合并 | 转行 | 去掉 |
| `nowrap` | 合并 | 合并 | 不转行 | 去掉 |
| `pre` | 保留 | 保留 | 不转行 | 保留 |
| `pre-wrap` | 保留 | 保留 | 转行 | 挂 |
| `pre-line` | 保留 | 合并 | 转行 | 去掉 |

## 示例

```css
p { white-space: normal; }
p { white-space: nowrap; }
p { white-space: pre; }
p { white-space: nowrap; }
p { white-space: pre-wrap; }
p { white-space: pre-line; }
```

```html
<p>This is some      text. This is some text. This is some text.
    This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.</p>
```
