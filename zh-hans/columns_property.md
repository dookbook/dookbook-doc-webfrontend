TOPICS: columns property
        column-width property
        column-count property

# CSS 属性: `columns`

CSS **`columns`** 属性用来设置元素的**列宽**和**列数**。是 **`column-width`** 和 **`column-count`** 属性的**简写属性**。与所有简写属性一样，任何省略的子值都将设置为其初始值。

## CSS `column-width` 属性

CSS属性 **`column-width`** 建议一个**最佳列宽**。列宽是在添加另一列之前列将成为最大宽度。

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 浏览器将决定列的宽度。 |
| **length** | 指定列宽的长度。 |

## CSS `column-count` 属性

CSS属性 **`column-count`** 描述元素的**列数**。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 列的最佳数目将其中的元素的内容无法流出。 |
| **`auto`** | 列数将取决于其他属性，例如：*`column-width`*。 |

## 示例

```css
.newspaper {
  columns: 80px 2; /* 列宽为80px，列数为2 */
}
```

```html
<div class="newspaper">
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim placerat facer possim assum. Typi non habent claritatem insitam; est usus legentis in iis qui facit eorum claritatem. Investigationes demonstraverunt lectores legere me lius quod ii legunt saepius.
</div>
```
