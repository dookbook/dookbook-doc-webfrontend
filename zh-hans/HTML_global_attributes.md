TOPICS: HTML Global Attributes

# HTML 全局属性

全局属性是所有[[HTML]]元素共有的属性; 它们可以用于所有元素，即使属性可能对某些元素不起作用。

我们可以在所有的HTML元素上指定全局属性，甚至是在标准里没有指定的元素。这意味着任何非标准元素仍必须能够应用这些属性，即使使用这些元素意味着文档不再是HTML5兼容的。
例如，虽然`<foo>`不是一个有效的HTML元素，但是HTML5兼容的浏览器隐藏了标记为`<foo hidden>...<foo>`的内容。

## 全局属性列表

| 属性 | 描述 | 状态 |
| :--- | :--- | --- |
| [**`id`**](/zh-hans/webfrontend/id_attribute) | 定义**唯一标识符**（**ID**），该标识符在整个文档中必须是**唯一**的。 其目的是在链接（使用片段标识符），脚本或样式（使用CSS）时标识元素。 | 可用 |
| [**`class`**](/zh-hans/webfrontend/class_attribute) | 一个以**空格分隔**的元素的类名（classes）列表，它允许CSS和JavaScript通过类选择器 (class selectors) 或DOM方法`document.getElementsByClassName()`来*选择*和*访问*特定的元素。 | 可用 |
| [**`title`**](/zh-hans/webfrontend/title_attribute) | 包含表示与其所属元素相关信息的**建议文本**。 这些信息通常可以作为提示呈现给用户，但不是必须的。 | 可用 |
| [**`hidden`**](/zh-hans/webfrontend/hidden_attribute) | *布尔属性*表示该元素尚未或不再相关。例如，它可用于隐藏在登录过程完成之前无法使用的页面元素。浏览器不会呈现此类元素。不得使用此属性隐藏可合法显示的内容。 | 可用 |
| [**`lang`**](/zh-hans/webfrontend/lang_attribute) | 帮助定义元素的**语言**：不可编辑元素所在的语言，或者应该由用户编写的可编辑元素的语言。该属性包含一个“语言标记”(由用连字符分隔的“语言子标记”组成)，格式在 [Tags for Identifying Languages (BCP47)](https://www.ietf.org/rfc/bcp/bcp47.txt) 中定义。`xml:lang` 优先于它。 | 可用 |
| [**`tabindex`**](/zh-hans/webfrontend/tabindex_attribute) | *整数属性*，指示元素是否可以获取输入焦点（可聚焦），是否应该参与顺序键盘导航，如果是，则表示哪个位置。| 可用 |
| [**`style`**](/zh-hans/webfrontend/style_attribute) | 含要应用于元素的[[CSS]]样式声明。 请注意，建议在单独的文件中定义样式。 该属性和[`<style>`](/zh-hans/webfrontend/<style>)元素主要用于快速样式化，例如用于测试目的。 | 可用 |
| [**`data-`**](/zh-hans/webfrontend/data-_attribute) | 一类**自定义数据属性**，它赋予我们在所有 HTML 元素上嵌入自定义数据属性的能力，并可以通过脚本(一般指JavaScript)与HTML之间进行专有*数据的交换*。所有这些自定义数据属性都可以通过所属元素的 `HTMLElement` 接口来访问。 `HTMLElement.dataset` 属性可以访问它们。 | 可用 |
| [`contenteditable`](/zh-hans/webfrontend/contenteditable_attribute) | 一个*枚举属性*（*enumerated attribute*），表示元素是否**可被用户编辑**。 如果可以，浏览器会调整元素的部件（widget）以允许编辑。<br> &nbsp;- `true` 或者*空字符串*，表明元素是**可被编辑的** <br> &nbsp;- `false`，表明元素**不能被编辑** | 可用 |
| [`accesskey`](/zh-hans/webfrontend/accesskey_attribute) | 提供了为当前元素生成**键盘快捷键**的*提示*。这个属性由空格分隔的字符列表组成。浏览器应该使用在计算机键盘布局上存在的**第一个**。 | 可用 |
| [`autocapitalize`](/zh-hans/webfrontend/autocapitalize_attribute) | 控制文本输入在用户输入/编辑时是否自动以及如何**自动大写**。 它可以具有以下值：<br> &nbsp;- `off` 或 `none`，没有应用自动大写（所有字母都默认为小写字母）<br> &nbsp;- `on` or `sentences`， 每个**句子**的第一个字母默认为*大写字母*;所有其他字母都默认为*小写字母* <br> &nbsp;- `words`，每个**单词**的第一个字母默认为*大写字母*;所有其他字母都默认为*小写字母* <br> &nbsp;- `characters`，所有的**字母**都应该默认为*大写* | 可用 |
| [`draggable`](/zh-hans/webfrontend/draggable_attribute) | 一种*枚举属性*，指示是否可以 使用 **Drag and Drop API** 拖动元素。它可以有以下的值：<br> &nbsp;- `true`, 这表明元素**可能被拖动** <br> &nbsp;- `false`, 这表明元素**可能不会被拖动** | 可用 |
| [`dir`](/zh-hans/webfrontend/dir_attribute) | 一个指示元素中**文本方向**的*枚举属性*。它的取值如下：<br> &nbsp;- `ltr`, 指**从左到右**，用于那种从左向右书写的语言（比如*英语*） <br> &nbsp;- `rtl`, 指**从右到左**，用于那种从右向左书写的语言（比如*阿拉伯语*） <br> &nbsp;- `auto`, 指由[用户代理](/zh-hans/glossary/User_Agent)决定方向。它在解析元素中字符时会运用一个基本算法，直到发现一个具有强方向性的字符，然后将这一方向应用于整个元素 | 可用 |
| [`inputmode`](/zh-hans/webfrontend/inputmode_attribute) | 向浏览器提供有关在编辑此元素或其内容时要使用的**虚拟键盘配置**类型的提示。主要用于 [`<input>`](/zh-hans/webfrontend/<input>)元素，但在[contenteditable](/zh-hans/webfrontend/contenteditable_attribute)模式下可用于任何元素。 | 可用 |
| [`is`](/zh-hans/webfrontend/is_attribute) | 允许您指定标准HTML元素应该像**已注册的自定义内置元素**一样。 | 可用 |
| [`itemid`](/zh-hans/webfrontend/itemid_attribute) | 项的唯一全局标识符。 | 可用 |
| [`itemprop`](/zh-hans/webfrontend/itemprop_attribute) | 用于向项添加属性。 每个HTML元素都可以指定一个`itemprop`属性，其中一个`itemprop`由一个名称和值对组成。 | 可用 |
| [`itemref`](/zh-hans/webfrontend/itemref_attribute) | 只有不是具有`itemscope`属性的元素的后代，它的属性才可以与使用`itemref`项目相关联。它提供了元素ID列表（而不是`itemid`s）以及文档中其他位置的其他属性。 | 可用 |
| [`itemscope`](/zh-hans/webfrontend/itemscope_attribute) | `itemscope`（通常）与`itemtype`一起使用，以指定包含在关于特定项目代码块中的HTML。 `itemscope`创建Item并定义与之关联的`itemtype`的范围。 `itemtype`是描述项及其属性上下文的词汇表（例如schema.org）的有效URL。 | 可用 |
| [`itemtype`](/zh-hans/webfrontend/itemtype_attribute) | 指定将用于在数据结构中定义`itemprop`（项属性）的词汇表的URL。 `itemscope`用于设置数据结构中按`itemtype`设置的词汇表的生效范围。 | 可用 |
| [`slot`](/zh-hans/webfrontend/slot_attribute) | 将**shadow DOM**阴影关联树中的一个沟槽分配给一个元素：具有`slot`属性的元素被分配给由[`<slot>`](/zh-hans/webfrontend/<slot>)元素创建的沟槽，其`name`属性的值与`slot`属性的值匹配。 | 可用 |
| `contextmenu` | [`<menu>`](/zh-hans/webfrontend/<menu>) 的id ，作为该元素的上下文菜单。 | **废弃** |
