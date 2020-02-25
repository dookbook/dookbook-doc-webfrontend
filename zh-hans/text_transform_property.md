TOPICS: text-transform property
AUTHORS: 紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei
         Bayes; 827130441@qq.com; github:coconilu
         xgqfrms; xgqfrms@github.com; github:xgqfrms

# CSS 属性: `text-transform`

**`text-transform`** CSS属性指定**如何将元素的文本大写**。它可以用于**使文本显示为全大写或全小写**，也可单独对每一个单词进行操作。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 默认。定义带有小写字母和大写字母的标准的文本。|
| **`capitalize`** | 文本中的每个单词以大写字母开头。|
| **`uppercase`** | 文本大写字母。|
| **`lowercase`** | 文本小写字母。|
| **`inherit`** | 规定应该从父元素继承 `text-transform` 属性的值。|

## 示例

```css
p.uppercase { text-transform:uppercase; }
p.lowercase { text-transform:lowercase; }
p.capitalize { text-transform:capitalize; }
```

```html
<p class="uppercase">This is some text.</p>
<p class="lowercase">This is some text.</p>
<p class="capitalize">This is some text.</p>
```
