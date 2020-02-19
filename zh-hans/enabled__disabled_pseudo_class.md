TOPICS: :enabled
        :disabled
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 伪类: `:enabled`、`:disabled`

**`:enabled`** CSS伪类表示任何启用的元素。如果一个元素能够被激活（如选择、点击或接受文本输入）或获取焦点，则该元素是启用的。元素还有一个禁用的状态，在被禁用时，元素不能被激活或获取焦点。

**`:disabled`** CSS伪类表示任何被禁用的元素。如果一个元素不能被激活（如选择、点击或接受文本输入）或获取焦点，则该元素处于被禁用状态。元素还有一个启用状态，在启用状态下，元素可以被激活或获取焦点。

## 示例

下面的代码，当文本输入框处于启用状态时，输入框的文本是中绿色，当处于禁用状态时，输入框的文本是灰色。这样可以把元素是否可用反馈给用户。

```html
<form action="url_of_form">
  <label for="FirstField">First field (enabled):</label> <input type="text" id="FirstField" value="Lorem"><br />
  <label for="SecondField">Second field (disabled):</label> <input type="text" id="SecondField" value="Ipsum" disabled="disabled"><br />
  <input type="submit" value="Submit" />
</form>
```

```css
input:enabled {
  color: #22AA22;
}

input:disabled {
  color: #D9D9D9;
}
```
