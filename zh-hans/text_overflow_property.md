TOPICS: text-overflow property

# CSS 属性: `text-overflow`

**`text-overflow`** CSS属性设置如何向用户发送隐藏的溢出内容信号。 可以剪切，显示省略号（`'…'`）或显示自定义字符串。

`text-overflow`属性不会强制发生溢出。要使文本溢出其容器，您必须设置其他CSS属性：**`overflow`** 和 **`white-space`**。

`text-overflow`属性仅影响沿其内联进度方向溢出了块容器元素的内容（例如，不溢出框底部的文本）。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`clip`** | 此属性的默认值。此关键字值将在内容区域的限制处截断文本，因此截断可能发生在字符中间。要限制字符之间的过渡，可以将`text-overflow`指定为空字符串（如果目标浏览器支持的话）: `text-overflow: '';`。|
| **`ellipsis`** | 这个关键字的意思是“用一个省略号 (`'…'`, U+2026 HORIZONTAL ELLIPSIS)来表示被截断的文本”。这个省略号被添加在内容区域中，因此会减少显示的文本。如果空间太小到连省略号都容纳不下，那么这个省略号也会被截断。|

## 示例

```css
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* BOTH of the following are required for text-overflow */
  white-space: nowrap;
  overflow: hidden;
}

.overflow-visible {
  white-space: initial;
}

.overflow-clip {
  text-overflow: clip;
}

.overflow-ellipsis {
  text-overflow: ellipsis;
}

.overflow-string {
  /* Not supported in most browsers,
     see the 'Browser compatibility' section below */
  text-overflow: " ..]";
}
```

```html
<p class="overflow-visible">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-clip">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-ellipsis">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-string">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
```
