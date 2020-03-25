TOPICS: transition property
        transition-property property
        transition-duration property
        transition-timing-function property
        transition-delay property

# CSS 过渡属性: `transition`

**`transition`** CSS 属性是 **`transition-property`**，**`transition-duration`**，**`transition-timing-function`**
和 **`transition-delay`** 的简写属性。

过渡可以为一个元素在不同状态之间切换的时候定义不同的过渡效果。比如在不同的伪元素之间切换，像是 `:hover`，`:active` 或者通过 JavaScript 实现的状态变化。

`transition`属性可以被指定为一个或多个 CSS 属性的过渡效果，多个属性之间用逗号进行分隔。当`transition`属性的值个数超过可以接收的值的个数时，多余的值都会被忽略掉，不再进行解析

## CSS 过渡属性的名称 `transition-property`

**`transition-property`** 指定应用**过渡属性的名称**。

!!! warn "注意"
    可被用于动画的属性集合文章近期将会变更，应该避免使用列表中出现的但目前没有动画的属性。否则，将会出现一些不可预料的结果。
    如果指定简写属性（比如 `background`），那么其完整版中所有可以动画的属性都会被应用过渡。

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 没有属性会获得过渡效果 |
| **`all`** | 所有属性都将获得过渡效果 |
| **property** | 定义应用过渡效果的 CSS 属性名称列表，列表以逗号分隔 |
| **ident** | 属性名称。由小写字母 `a` 到 `z`，数字 `0` 到 `9`，下划线（`_`）和破折号（`-`）。第一个非破折号字符不能是数字。同时，不能以两个破折号开头 |

## CSS 过渡时间属性 `transition-duration`

**`transition-duration`** 属性以**秒**或**毫秒**为单位指定**过渡动画所需的时间**。默认值为 `0s`，表示不出现过渡动画。

| 属性值 | 描述 |
| :--- | :--- |
| **time** | 规定**完成过渡效果需要花费的时间**（以**秒**或**毫秒**计）。默认值是 `0`，意味着不会有效果 |

## CSS 过渡时间属性 `transition-timing-function`

CSS `transition-timing-function` 属性用来描述这个中间值是怎样计算的。实质上，通过这个函数会建立一条加速度曲线，因此在整个`transition`变化过程中，变化速度可以不断改变。

这条加速度曲线被计时功能所定义，之后作用到每个CSS属性的过渡。

| 属性值 | 描述 |
| :--- | :--- |
| **`linear`** | 规定以**相同速度开始至结束**的过渡效果（等于`cubic-bezier(0,0,1,1)`） |
| **`ease`** | 规定**慢速开始**，然后**变快**，然后**慢速结束**的过渡效果（`cubic-bezier(0.25,0.1,0.25,1)`） |
| **`ease-in`** | 规定以**慢速开始**的过渡效果（等于`cubic-bezier(0.42,0,1,1)`） |
| **`ease-out`** | 规定以**慢速结束**的过渡效果（等于`cubic-bezier(0,0,0.58,1)`） |
| **`ease-in-out`** | 规定以**慢速开始**和**结束**的过渡效果（等于`cubic-bezier(0.42,0,0.58,1)`） |
| **`cubic-bezier(n,n,n,n)`** | 在 `cubic-bezier` 函数中定义**自己的值**。可能的值是 `0` 至 `1` 之间的数值 |

## CSS 过渡开始等待时间属性 `transition-delay`

CSS **`transition-delay`** 属性规定了在过渡效果**开始作用之前需要等待的时间**。值以**秒**（`s`）或**毫秒**（`ms`）为单位，表明动画过渡效果将在何时开始。

| 属性值 | 描述 |
| :--- | :--- |
| **time** | 指定**秒**或**毫秒**数之前要等待切换效果开始 |

## 示例

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition-property: width; /* 指定width为过渡属性 */
  transition-duration: 2s; /* 过渡动画以2s内完成 */
  transition-timing-function: ease-in; /* 过渡动画以慢速开始 */
  transition-delay: 1s; /* 等待一秒执行过渡动画 */

  /* 以下是简写 */
  /* transition: width 5s ease-in 1s; */
}

div:hover {
  width:300px;
}
```

```html
<div></div>
<p>将鼠标移动至块上查看过渡动画效果.</p>
```
