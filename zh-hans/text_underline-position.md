TOPICS: text-underline-position property

# CSS 属性: `text-underline-position`

当 [**`text-decoration`**](/zh-hans/webfrontend/text-decoration_property) 属性的值设置为 *`underline`* 之后，
可以用 **`text-underline-position`** 属性为其设置**下划线的位置**。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`auto`** | 用户代理 会根据自己的算法来确认下划线是放在字母基线上还是 放在字母基线下方。 |
| **`under`** | 强制下划线的位置为**字母基线的下方**，在这个位置，下划线不会穿过任何字母，这样能确保数学方程式或者化学式的下标不会被下划线阻挡。 |
| **`left`** | 在**垂直排版模式下**，使下划线的位置在文字的**左侧**，在水平排版模式下，和 *`under`* 相同。 |
| **`right`** | 在**垂直排版模式下**，使下划线的位置在文字的**右侧**，在水平排版模式下，和 *`under`* 相同。 |

## 示例

由于 **`text-underline-position`** 属性可以继承，且无法用 [**`text-decoration`**](/zh-hans/webfrontend/text-decoration_property)
简写属性重置，所以应当在全局级别设置其值。比如，*`under`* 值对一篇包括大量使用下标的数学或者化学公式的文档是非常有用的。

```css
:root {
  text-underline-position: under;
}
```
