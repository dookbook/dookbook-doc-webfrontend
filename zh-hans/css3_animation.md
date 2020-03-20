TOPICS: CSS3 动画
        animation property
        animation-name property
        animation-duration property
        animation-timing-function property
        animation-delay property
        animation-iteration-count property
        animation-direction property
        animation-fill-mode property
        animation-play-state property
        @keyframes property

# CSS3 动画 （`animation`）

CSS3 可以创建**动画**，它可以取代许多**网页动画图像**、Flash 动画和 JavaScript 实现的效果。

动画属性可以逐渐地从一个值变化到另一个值，比如**尺寸大小**、**数量**、**百分比**和**颜色**。

## CSS3 `@keyframes` 规则

**`@keyframes`** 规则是创建动画。是指定一个 CSS 样式和动画将逐步从**目前的样式**更改为**新的样式**

指定的变化时发生时使用 **％**，或关键字"**from**"和"**to**"，这是和**0％**到**100％**相同。

**0％**是开头动画，**100％**是当动画完成。

## CSS3 动画属性

| 属性 | 说明 |
| :--- | :--- |
| **`animation`** | 所有动画属性的**简写属性**，除了 **`animation-play-state`** 属性 |
| **`animation-name`** | 指定**应用的一系列动画**，每个名称代表一个由 **`@keyframes`** 定义的动画序列 |
| **`animation-duration`** | 指定**一个动画周期的时长**。默认值为`0s`，表示无动画 |
| **`animation-timing-function`** | 指定CSS动画在每一动画周期中**执行的节奏** |
| **`animation-delay`** | 指定动画**何时开始**。默认是 `0` |
| **`animation-iteration-count`** | 指定动画在**结束前运行的次数**，可以是**1次**或**无限循环** |
| **`animation-direction`** | 指定是否应该**轮流反向播放动画** |
| **`animation-fill-mode`** | 指定动画在**执行之前**和**之后**如何将样式应用于其目标 |
| **`animation-play-state`** | 指定动画是否**正在运行**或**已暂停** |

## `animation-name` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **keyframename** | 指定要绑定到选择器的**关键帧的名称** |
| **`none`** | 指定有没有动画（可用于覆盖从级联的动画） |

## `animation-duration` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **time** | 指定动画**播放完成花费的时间**。默认值为`0`，意味着没有动画效果 |

## `animation-timing-function` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`linear`** | 动画从头到尾的**速度是相同的** |
| **`ease`** | 默认。动画以**低速开始**，然后**加快**，在结束前**变慢** |
| **`ease-in`** | 动画以**低速开始** |
| **`ease-out`** | 动画以**低速结束** |
| **`ease-in-out`** | 动画以**低速开始**和**结束** |
| **`cubic-bezier(n,n,n,n)`** | 在 `cubic-bezier` 函数中自己的值。可能的值是从 `0` 到 `1` 的数值 |

## `animation-delay` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **time** | 可选。定义动画**开始前等待的时间**，以**秒**或**毫秒**计。默认值为 `0` |

## `animation-iteration-count` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **n** | **一个数字**，定义**应该播放多少次动画** |
| **`infinite`** | 指定动画应该播放**无限次**（永远） |

## `animation-direction` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 默认值。动画按**正常播放** |
| **`reverse`** | 动画**反向播放** |
| **`alternate`** | 动画在**奇数次（1、3、5...）正向播放**，在**偶数次（2、4、6...）反向播放** |
| **`alternate-reverse`** | 动画在**奇数次（1、3、5...）反向播放**，在**偶数次（2、4、6...）正向播放** |

## `animation-fill-mode` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认值。动画在动画执行之前和之后不会应用任何样式到目标元素 |
| **`forwards`** | 目标将保留由执行期间遇到的最后一个关键帧计算值。 最后一个关键帧取决于 *`animation-direction`* 和 *`animation-iteration-count`* 的值： |
| **`backwards`** | 动画将在应用于目标时立即应用第一个关键帧中定义的值，并在 *`animation-delay`* 期间保留此值。 第一个关键帧取决于 *`animation-direction`* 的值： |
| **`both`** | 动画遵循 *`forwards`* 和 *`backwards`* 的规则。也就是说，动画会在两个方向上扩展动画属性 |

## `animation-play-state` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`paused`** | 当前动画以被停止 |
| **`running`** | 当前动画正在运行 |

## 示例

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation-name: mymove; /* 绑定 @keyframes 为 mymove 的名称 */
  animation-duration: 2s; /* 两秒内完成动画 */
  animation-timing-function: linear; /* 以匀速播放动画 */
  animation-delay: 3s; /* 等待3s启动动画 */
  animation-iteration-count: 2; /* 动画将执行两次 */
  animation-direction: alternate; /* 以奇数正向播放，偶数次反向播放 */
  animation-fill-mode: forwards; /* 将停留在第一帧，停留帧取决于 animation-iteration-count 和 animation-direction 属性值 */
  animation-play-state: running; /* 允许动画执行 */
}

/* 简写示例，等同于上面代码 */
div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation: mymove 2s linear 3s 2 alternate forwards;
  animation-play-state: running;
}

/* 动画演变过程 */
@keyframes mymove {
  from { left: 0; }
  to { left: 200px; }
}
```
