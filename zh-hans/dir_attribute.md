TOPICS: dir attribute

# HTML 全局属性: `dir`

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)**`dir`**是一个指示元素中文本方向的枚举属性。

## 属性值

| 值 | 描述 |
| :-- | :-- |
| `ltr` | 默认。从左向右的文本方向。|
| `rtl` | 从右向左的文本方向。|
| `auto` | 让浏览器根据内容来判断文本方向。仅在文本方向未知时推荐使用。|

## 使用说明

- 这个属性对有不同语义的[`<bdo>`](/zh-hans/webfrontend/<bdo>)元素是必须的。
- 这个属性在[`<bdi>`](/zh-hans/webfrontend/<bdi>)元素中不可继承。未赋值时，它的默认值是`auto`。
- 这个属性可以被CSS属性 *`direction`* 和 *`unicode-bidi`* 覆盖，如果CSS网页有效且该元素支持这些属性的话。
- 由于文本的方向是和内容的语义而不是和表现相关，因此有可能的话，网页开发者使用这一属性而非CSS属性是被推荐的。这样，即使在不支持CSS或禁CSS的浏览器中，文本也会正常显示。
- `auto` 应当用于方向未知的数据，如用户输入的数据，最终保存在数据库中的数据。

## 示例

```html
<bdo dir="rtl">文本方向从右到左!</bdo>
```

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- 对应这个属性的[`HTMLElement.dir`](/zh-hans/webfrontend/HTMLElement.dir)。
