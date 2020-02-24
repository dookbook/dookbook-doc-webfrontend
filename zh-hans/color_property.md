TOPICS: color property

# CSS 属性: `color`

**`color`** 属性指定文本的颜色

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| color_name | 规定颜色值为颜色名称的颜色（比如 **`red`**）|
| hex_number | 规定颜色值为十六进制值的颜色（比如 **`#ff0000`**）|
| rgb_number | 规定颜色值为 **`rgb`** 代码的颜色（比如 **`rgb(255, 0, 0)`**）|
| `inherit` | 规定应该从父元素继承颜色。|

## 示例

```css
p { color: red; }
p { color: #f00; }
p { color: #ff0000; }
p { color: rgb(255,0,0); }
p { color: rgb(100%, 0%, 0%); }
p { color: hsl(0, 100%, 50%); }

/* 50% translucent */
p { color: #ff000080; }
p { color: rgba(255, 0, 0, 0.5); }
p { color: hsla(0, 100%, 50%, 0.5); }
```
