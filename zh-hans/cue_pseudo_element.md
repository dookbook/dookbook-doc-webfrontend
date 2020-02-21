TOPICS: ::cue

# CSS 伪元素: `::cue`

**`::cue`** CSS 伪元素匹配**所选元素中的WebVTT提示**。这可以用于在VTT轨道的媒体中使用字幕和其他线索。

只有CSS一小部分属性可以与 `::cue` 伪元素一起使用：

- `color`
- `opacity`
- `visibility`
- `text-decoration` 及其长期特性: `text-decoration-line`, `text-decoration-color`,和 `text-decoration-style`
- `text-shadow`
- `background` 及其长期特性: `background-color`, `background-clip`, `background-image`,
`background-origin`, `background-position`, `background-repeat`, `background-size`,
`background-attachment`, 和 `background-blend-mode`
- `outline` 及其长期特性: `outline-color`, `outline-style`, `outline-width`
- `font` 及其长期特性: `font-kerning`, `font-style`, `font-variant`,
`font-variant-numeric`, `font-variant-position`, `font-variant-east-asian`, `font-variant-caps`,
`font-variant-alternates`, `font-variant-ligatures`, `font-synthesis`, `font-feature-settings`,
`font-language-override`, `font-weight`, `font-size`, `font-size-adjust`, `font-stretch`, and `font-family`
- `line-height`
- `white-space`
- `text-combine-upright`
- `ruby-position`

属性应用于整个提示集，就像它们是单个单元一样。唯一的例外是背景及其简写属性可以单独应用于每个提示，以避免创建框并遮盖意外大面积的媒体。

## 示例

以下CSS设置提示样式，使文本为白色，背景为半透明黑盒。

```css
::cue {
  color: #fff;
  background-color: rgba(0, 0, 0, 0.6);
}
```
