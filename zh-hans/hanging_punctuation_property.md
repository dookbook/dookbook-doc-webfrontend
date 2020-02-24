TOPICS: hanging-punctuation property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `hanging-punctuation`

CSS 属性 **`hanging-punctuation`** 指定了**标点符号应该放在文本句子的开头还是结尾**。悬挂标点符号可能被放在线框外。

## 语法

这个属性可被指定多个值，可以是**一个值**，也可以是**两个值**，或者是**三个值**。

- **一个值** 语法：在下面列表中的任意一个值。
- **两个值** 语法：
    - 或者与以下任何一个一起使用，并以它们结尾：**`last`**, **`allow-end`**或 **`force-end`**
    - 或者与以下任何一个一起使用，并以它们开头：**`first`**, **`allow-end`**或 **`force-end`**
- **三个值** 语法:
    - 或者 **`first`**, **`allow-end`**, 和 **`last`**.
    - 或者 **`first`**, **`force-end`**, 和 **`last`**.

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 没有字符挂起。 |
| **`first`** | 显示元素的第一个格式化行开头的括号或引号。|
| **`last`** | 显示元素的最后一个格式化行结尾的括号或引号。|
| **`force-end`** | 显示行结尾处的句号或逗号。|
| **`allow-end`** | 如果预先没有其它适合的来适应的，则在行尾显示句号或逗号。|

## 示例

```css
p {
  hanging-punctuation: first last;
  margin: 0.5rem;
}
```

```html
<p>“Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur dignissim nunc mauris, et sollicitudin est scelerisque sed. Praesent laoreet tortor massa, sit amet vulputate nulla pharetra ut.”</p>
```
