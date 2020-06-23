TOPICS: font-feature-settings property

# CSS 属性: `font-feature-settings`

CSS属性 **`font-feature-settings`** 可让您控制OpenType字体中的高级印刷功能。

!!! warn ""
    Web开发者应该尽可能的使用类似 [**`font-variant`**](/zh-hans/webfrontend/font-variant_property)
    这样的短标记属性或者相关的速记标识属性等，类似 `font-variant-ligatures`，
    `font-variant-caps`，`font-variant-east-asian`，`font-variant-alternates`，
    `font-variant-numeric` 或 `font-variant-position`。
    该属性是一个比较偏底层的功能接口，用于解决由于没有其他方法去访问和设置OpenType字体某些特性而无法解决一些特殊功能需求。
    特别需要注意的是，该CSS属性不应该用来开启大写字母转换。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 文本使用默认设置进行布局。 |
| **feature-tag-value** | 在呈现文本时，OpenType要素标记值的列表被传递到文本布局引擎以启用或禁用字体特征。标签始终是4个ASCII字符的 `<string>` 。如果是U + 20 - U + 7E代码点范围以外的字符或字符个数不对，则整个属性无效。<br>值是一个正整数。两个关键字`on`和`off`分别是`1`和`0`的同义词。如果未设置任何值，则默认值为`1`。对于非布尔型OpenType功能（例如，文体替代），该值意味着要选择特定的字形；对于布尔值，它是一个开关。 |

## 示例

```css
/* 使用小写备用字形 */
.smallcaps { font-feature-settings: "smcp" on; }

/* 将大写和小写都转换为小写（也影响标点符号） */
.allsmallcaps { font-feature-settings: "c2sc", "smcp"; }

/* 启用历史形式 */
.hist { font-feature-settings: "hist"; }

/* 禁用常用连字，通常默认情况下启用 */
.noligs { font-feature-settings: "liga" 0; }

/* 启用表格（等距）图形 */
td.tabular { font-feature-settings: "tnum"; }

/* 启用自动分数 */
.fractions { font-feature-settings: "frac"; }

/* 使用第二个可用的斜线字符 */
.swash { font-feature-settings: "swsh" 2; }

/* 启用样式集7 */
.fancystyle {
  font-family: Gabriola; /* 在Windows 7和Mac OS上可用 */
  font-feature-settings: "ss07";
}
```
