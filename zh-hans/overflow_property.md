TOPICS: overflow property
        overflow-x property
        overflow-y property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         ntnyq; ntnyq13@gmail.com; github:ntnyq
         weiqinl; 772863869@qq.com; github:LiuwqGit
         庄引; zhuangyin8@gmail.com; github:zhuangyin8
         杜维康; VictorDu@mozilla.net; mdn:VictorDu
         xgqfrms; xgqfrms@github.com; github:xgqfrms
         YF; yfdyh000@mozilla.net; mdn:yfdyh000
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Teoli; teoli@mozilla.net; mdn:teoli
         Jimmie Felidae; evolution.jimmy@gmail.com; github:evojimmy

# CSS 控制内容溢出属性: `overflow`

CSS属性 **`overflow`** 定义当一个元素的内容太大而无法适应块级格式化上下文时候该做什么。它是 **`overflow-x`** 和 **`overflow-y`** 的简写属性

这个选项包含剪切，显示滚动条，或者显示 从容器溢出到周围区域的内容。

指定除`visible`(默认值)以外的值将创建一个新的 块级格式化上下文. 这在技术层面上是必须的——如果一个浮动元素和滚动条相交，它会在每个滚动步骤后强行重新包装内容，从而导致慢滚动体验。

为使 `overflow` 有效果，块级容器必须有一个指定的高度（`height`或者`max-height`）或者将`white-space`设置为`nowrap`。

!!! warn "注意"
    设置一个轴为`visible`（默认值），同时设置另一个轴为不同的值，会导致设置`visible`的轴的行为会变成`auto`。 注意:

!!! warn "注意"
    即使将`overflow`设置为`hidden`，也可以使用JavaScript `Element.scrollTop` 属性来滚动HTML元素。

从下面列表中选出一个或两个关键字来指定`overflow` 属性。如果指定了两个关键字，第一个关键字应用于`overflow-y`，第二个关键字应用于`overflow-x`。否则，`overflow-x`和`overflow-y`都设置为相同的值。

!!! warn ""
    注意: 在Firefox 63之前，这些值是反向的，第一个值应用于`overflow-x`，第二个值应用于`overflow-`y。Firefox 63更新了这个顺序，以匹配对规范的更改。此更改是为了匹配使用新逻辑属性`overflow-block`和`overflow-inline`时的顺序。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`visible`** | 默认值。内容不会被修剪，可以呈现在元素框之外。|
| **`hidden`** | 如果需要，内容将被剪裁以适合填充框。不提供滚动条。|
| **`scroll`** | 如果需要，内容将被剪裁以适合填充框。浏览器显示滚动条，无论是否实际剪切了任何内容。 （这可以防止滚动条在内容更改时出现或消失。）打印机仍可能打印溢出的内容。|
| **`auto`** | 取决于用户代理。 如果内容适合填充框内部，则它看起来与可见内容相同，但仍会建立新的块格式化上下文。 如果内容溢出，桌面浏览器会提供滚动条。|

## CSS 属性 `overflow-x`

当一个块级元素的内容在**水平方向发生溢出时**，CSS属性 **`overflow-x`** 决定应该截断溢出内容，或者显示滚动条，或者直接显示溢出内容。

## CSS 属性 `overflow-y`

当一个块级元素的内容在**垂直方向发生溢出时**，CSS属性 **`overflow-y`** 决定应该截断溢出内容，或者显示滚动条，或者直接显示溢出内容

## 示例

### 简单示例

```css
p {  
  width: 12em;
  height: 6em;
  border: dotted;
  overflow: visible; /* 内容不会被修剪 */
}

p { overflow: hidden; /* 不显示滚动条 */  }

p { overflow: scroll; /* 始终显示滚动条 */  }

p { overflow: auto; /* 必要时显示滚动条 */  }
```

```html
<p>visible (default)
Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.</p>
```

### overflow-y

```css
#div1,
#div2,
#div3 {
  border: 10px dotted blue;
  width:  200px;
  height: 100px;
}

#div1 { overflow-y: visible; }
#div2 { overflow-y: auto; }
#div3 { overflow-y: hidden; }
```

```html
<div id="div1">
  <h1><code>overflow-y:visible;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>

<div id="div2">
  <h1><code>overflow-y:auto;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>

<div id="div3">
  <h1><code>overflow-y:hidden;</code></h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
</div>
```
