TOPICS: :left
        :right

# CSS 伪类: `:left`、`:right`

**`:left`** CSS 伪类需要和@规则 **`@page`** 配套使用, 对打印文档的左侧页设置CSS样式.

**`:right`** CSS 伪类必须与@规则 **`@page`** 一起配套使用，表示打印文档的所有右页。

打印文档的"左"或"右"是由书写方向相关的. 举个栗子, "从左到右"的书写方向中第一页应当使用 `:right` 配置; "从右至左"的书写方向中第一页应当使用 `:left` 配置.

!!! warn "注意“
    并不是所有样式属性都能应用在此选择器内. 仅仅 `margin`, `padding`, `border`, 和 `background` 等打印时需要的属性可以使用. 其他属性将直接忽略,
    并且可以使用的属性也只会在打印时生效, 显示时不会生效.

## 示例

```css
@page :left {
  margin: 2in 3in;
}
```

```css
@page :right {
  margin: 2in 3in;
}
```
