TOPICS: column-rule property
        column-rule-width property
        column-rule-style property
        column-rule-color property

# CSS Line property between columns: `column-rule`

In a multi-column layout, the **`column-rule`** property specifies **the straight line between columns**,
also known as "rules". **`column-rule-width`**, **`column-rule-style`** and **`column-rule-color`**
are shorthand propertys.

## Property value

| Property Value | Description |
| :--- | :--- |
| **column-rule-width** | Set the width of the **line drawn between each column in the multi-column layout. The property value can be set by the property value of [*`border-width`*](/en/webfrontend/border-width_property). |
| **column-rule-style** | Set the style of the **line drawn between each column in the multi-column layout. The property value can be set by the property value of [*`border-style`*](/en/webfrontend/border-style_property). |
| **column-rule-color** | Set the **line color** drawn between the columns in the multi-column layout. The property value can be set by [*CSS color*](/en/webfrontend/css_color). |

## 示例

```css
.newspaper {
  column-count: 3; /* Divide the column into 3 columns */
  column-gap: 40px; /* The spacing between the columns is divided into 40px */
  column-rule: 4px outset #f00; /* The line between the columns is 4px and the solid line is red */
}
```

```html
<div class="newspaper">
When I was young, I dreamed of changing the world; when I was mature, I found that I could not change the world. I shortened my eyes and decided to only change my country; when I entered the twilight years, I found that I did not To change our country, my last wish is to change my family, but this is also impossible. When I was lying on the bed now and was about to die, I suddenly realized that if I only changed myself at first, then I might change my family; with the help and encouragement of my family, I might do something for the country; Then, who knows? I might even change this world.
</div>
```
