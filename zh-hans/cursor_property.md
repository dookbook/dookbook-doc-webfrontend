TOPICS: cursor property

# CSS 鼠标光标属性: `cursor`

**`cursor`** CSS属性定义**鼠标指针悬浮在元素上方显示的鼠标光标**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`default`** | 默认光标，通常是一个**箭头** |
| **`auto`** | 默认。浏览器设置的光标 |
| **`crosshair`** | 光标呈现为**十字线** |
| **`pointer`** | 光标呈现为指示链接的指针**一只手** |
| **`move`** | 此光标指示某对象**可被移动** |
| **`e-resize`** | 此光标指示矩形框的边缘**可被向右（东）移动** |
| **`ne-resize`** | 此光标指示矩形框的边缘**可被向上及向右移动（北/东）** |
| **`nw-resize`** | 此光标指示矩形框的边缘**可被向上及向左移动（北/西）** |
| **`n-resize`** | 此光标指示矩形框的边缘**可被向上（北）移动** |
| **`se-resize`** | 此光标指示矩形框的边缘**可被向下及向右移动（南/东）** |
| **`sw-resize`** | 此光标指示矩形框的边缘**可被向下及向左移动（南/西）** |
| **`s-resize`** | 此光标指示矩形框的边缘**可被向下移动（北/西）** |
| **`w-resize`** | 此光标指示矩形框的边缘**可被向左移动（西）** |
| **`text`** | 此光标指示**文本** |
| **`wait`** | 此光标指示**程序正忙**，通常是**一只表**或**沙漏** |
| **`help`** | 此光标指示**可用的帮助**，通常是**一个问号**或**一个气球** |
| **`none`** | **无指针被渲染** |
| **`context-menu`** | 指针下有**可用内容目录** |
| **`progress`** | **程序后台繁忙**，用户仍可交互 (与*`wait`*不同) |
| **`cell`** | 指示**单元格可被选中** |
| **`vertical-text`** | 指示**垂直文字可被选中** |
| **`alias`** | **复制**或**快捷方式将要被创建** |
| **`copy`** | 指示**可复制** |
| **`no-drop`** | **当前位置不能扔下** |
| **`not-allowed`** | **不能执行** |
| **`all-scroll`** | 元素**可任意方向滚动** (平移) |
| **`col-resize`** | 元素**可被重设宽度**。通常被渲染为**中间有一条竖线分割的左右两个箭头** |
| **`row-resize`** | 元素**可被重设高度**。通常被渲染为**中间有一条横线分割的上下两个箭头** |
| **`ew-resize`** | 指示**双向重新设置大小** |
| **`ns-resize`** | 指示**双向重新设置大小** |
| **`nesw-resize`** | 指示**双向重新设置大小** |
| **`nwse-resize`** | 指示**双向重新设置大小** |
| **`zoom-in`** | 指示**可被放大** |
| **`zoom-out`** | 指示**可被缩小** |
| **`grab`** | **可抓取** |
| **`grabbing`** | **抓取中** |
| **url** | 需使用的**自定义光标的 URL**.<br>**注意**: 请在此列表的末端始终定义一种普通的光标，以防没有由 URL 定义的可用光标 |

## 示例

```html
<p>请把鼠标移动到单词上，可以看到鼠标指针发生变化：</p>
<span style="cursor:default;">default</span><br>
<span style="cursor:auto;">auto</span><br>
<span style="cursor:crosshair;">crosshair</span><br>
<span style="cursor:pointer;">pointer</span><br>
<span style="cursor:move;">move</span><br>
<span style="cursor:e-resize;">e-resize</span><br>
<span style="cursor:ne-resize;">ne-resize</span><br>
<span style="cursor:nw-resize;">nw-resize</span><br>
<span style="cursor:n-resize;">n-resize</span><br>
<span style="cursor:se-resize;">se-resize</span><br>
<span style="cursor:sw-resize;">sw-resize</span><br>
<span style="cursor:s-resize;">s-resize</span><br>
<span style="cursor:w-resize;">w-resize</span><br>
<span style="cursor:text;">text</span><br>
<span style="cursor:wait;">wait</span><br>
<span style="cursor:help;">help</span><br>
<span style="cursor:none;">none</span><br>
<span style="cursor:context-menu;">context-menu</span><br>
<span style="cursor:progress;">progress</span><br>
<span style="cursor:cell;">cell</span><br>
<span style="cursor:vertical-text;">vertical-text</span><br>
<span style="cursor:alias;">alias</span><br>
<span style="cursor:copy;">copy</span><br>
<span style="cursor:no-drop;">no-drop</span><br>
<span style="cursor:not-allowed;">not-allowed</span><br>
<span style="cursor:all-scroll;">all-scroll</span><br>
<span style="cursor:col-resize;">col-resize</span><br>
<span style="cursor:row-resize;">row-resize</span><br>
<span style="cursor:ew-resize;">ew-resize</span><br>
<span style="cursor:ns-resize;">ns-resize</span><br>
<span style="cursor:nesw-resize;">nesw-resize</span><br>
<span style="cursor:nwse-resize;">nwse-resize</span><br>
<span style="cursor:zoom-in;">zoom-in</span><br>
<span style="cursor:zoom-out;">zoom-out</span><br>
<span style="cursor:grab;">grab</span><br>
<span style="cursor:grabbing;">grabbing</span><br>
```
