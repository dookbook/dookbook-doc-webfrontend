TOPICS: tabindex attribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# HTML 全局属性: `tabindex`

**`tabindex`** [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) 指示其元素是否可以聚焦，以及它是否/在何处参与顺序键盘导航（通常使用!!!Tab!!!键，因此得名）。

它接受一个整数作为值，具有不同的结果，具体取决于整数的值：

- **负值** (通常是`tabindex=“-1”`)，表示元素是可聚焦的，但是不能通过键盘导航来访问到该元素，用JS做页面小组件内部键盘导航的时候非常有用。
- **`0`** 表示元素是可聚焦的，并且应该可以通过顺序的键盘导航到达，但是该 !!!Tab!!! 的顺序由用户代理决定，后者应该应用用户的平台约定。当您希望元素可聚焦并参与键盘导航而不是尝试自己管理选项卡顺序时，通常这是最佳使用值。
- **正值** 表示元素是可聚焦的，并且可以通过键盘导航来访问到该元素；每次用户按下 !!!Tab!!! 键时，它的相对顺序按照 **`tabindex`** 的数值递增而滞后获焦。
大多数平台通常提供反向标签功能，通常结合使用 !!!Shift!!! + !!!Tab!!! 会反转制表顺序。如果多个元素拥有相同的 **`tabindex`**，它们的相对顺序按照他们在当前DOM中的先后顺序决定。

如果我们在 [`<div>`](/zh-hans/webfrontend/<div>) 上设置了 `tabindex` 属性，它的子元素内容不能使用箭头键来滚动，除非我们在内容上也设置`tabindex`。

!!! warn "注意"
    `tabindex` 的最大值不应超过 **32767**。如果没有指定，它的默认值为 `-1`。

## 示例

```html
<a href="https://dookbook.info/" tabindex="2">DookBook</a><br/>
<a href="https://github.com/" tabindex="1">GitHub</a><br/>
<a href="http://www.google.com/" tabindex="3">Google</a>
<!--
    点击到1，按Tab键，依次跳到2、3
    点击3，跳转到其它地方
    点击2，跳转到3

    tabindex的跳转顺序为从小到大。如果直接点击模块中的tabindex序数最大的选项，则跳转到他处，或者不跳转。
-->
<p><b>注释：</b>请尝试使用键盘上的 "Tab" 键在链接之间进行导航。</p>
```

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- 反映这个属性的 [`HTMLElement.tabIndex`](/zh-hans/webfrontend/HTMLElement.tabIndex)
- `tabindex` 的可访问性问题：请见 [不要使用大于 0 的 Tabindex | Adrian Roselli](http://adrianroselli.com/2014/11/dont-use-tabindex-greater-than-0.html)。
