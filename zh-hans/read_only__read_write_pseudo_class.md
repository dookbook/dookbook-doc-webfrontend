TOPICS: :read-only
        :read-write

# CSS 伪类: `:read-only`、`:read-write`

**`:read-only`** CSS 伪类表示元素不可被用户编辑的状态（如锁定的文本输入框）。这个选择器不只是选择具有 **`readonly`** 属性的[**`<input>`**](/zh-hans/webfrontend/<input>)元素，它也会选择所有的不能被用户编辑的元素。

**`:read-write`** CSS 伪类代表一个元素（例如可输入文本的[**`<input>`**](/zh-hans/webfrontend/<input>)元素）可以被用户编辑。这个选择器不仅仅选择
[**`<input>`**](/zh-hans/webfrontend/<input>) 元素，它也会选择所有可以被用户编辑的元素，例如设置了
**`contenteditable`** 属性的 [**`<p>`**](/zh-hans/webfrontend/<p>) 元素。

## 示例: `:read-only`

```html
<input type="text" value="Type whatever you want here.">
<input type="text" value="This is a read-only field." readonly>
<p>This is a normal paragraph.</p>
<p contenteditable="true">You can edit this paragraph!</p>
```

```css
input { min-width: 25em; }
input:-moz-read-only { background: cyan; }
input:read-only { background: cyan; }

p:-moz-read-only { background: lightgray; }
p:read-only { background: lightgray; }
p[contenteditable="true"] { color: blue; }
```

## 示例: `:read-write`

```html
<input type="text" value="Type whatever you want here.">
<input type="text" value="This is a read-only field." readonly>
<p>This is a normal paragraph.</p>
<p contenteditable="true">You can edit this paragraph!</p>
```

```css
input { min-width: 25em; }
input:-moz-read-write { background: cyan; }
input:read-write { background: cyan; }

p:-moz-read-write { background: lightgray; }
p:read-write { background: lightgray; }
p[contenteditable="true"] { color: blue; }
```
