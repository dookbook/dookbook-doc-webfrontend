TOPICS: src property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 字体数据资源属性: `src`

**`@font-face`** 中的 **`src`** 描述符指定了包含**字体数据的资源**。**`@font-face`** 规则中需要指定这个属性。

它的值是一个有优先级的，以逗号分割的外部引用或者本地安装的字体名称。当需要使用字体时，用户代理（指浏览器的意思）将会使用以逗号分隔的参考集中能成功激活的第一个参考值。如果是包含无效数据的字体或者本地的字体资源不存在，用户代理将会忽略当前字体并且加载下一个字体。

与CSS中的其他URL一样，URL可以是相对的，在这种情况下，它相对于包含 **`@font-face`** 规则的样式表的位置进行解析。对于SVG字体，URL指向文档中定义的包含SVG字体的元素。
如果省略元素引用，则默认引用第一个定义字体。同样，字体容器只加载 **`@font-face`** 规则给定的其中一种字体。片段标识符用于指示要加载的字体。如果容器格式缺少定义的片段标识符方案，将会使用一个简单的基于1的索引方案（例如：第一个字体为“font-collection＃1”，第二个字体为“font-collection＃2”，等等）。

| 属性值 | 描述 |
| :--- | :--- |
| **`url() format()`** | 指定一个由 **`url`** 组成的外部引用，其后使用 **`format()`** 函数描述该URL引用的字体资源的格式的可选提示。格式提示包含逗号分隔的格式字符串列表，这些字符串表示众所周知的字体格式。如果用户代理不支持指定的格式，它将跳过下载字体资源。如果没有提供格式提示，则始终下载字体资源。|
| **`local()`** | 使用 **`local()`** 函数指定本地安装的字体的名称，该功能唯一地标识较大系列中的单个字体。该名称可以选择用引号引起来。|

## 示例

```css
@font-face {
  font-family: examplefont;
  /* url 值 */
  src: url(https://somewebsite.com/path/to/font.woff); /* 绝对网址 */
  src: url(path/to/font.woff);                         /* 相对网址 */
  src: url(path/to/font.woff) format("woff");          /* 显式格式 */
  src: url('path/to/font.woff');                       /* 引用网址 */
  src: url(path/to/svgfont.svg#example);               /* 片段识别字体 */

  /* 字体名称值 */
  src: local(font);      /* 未加引号的名字 */
  src: local(some font); /* 名称包含空格 */
  src: local("font");    /* 引用名称 */

  /* 多个项目 */
  src: local(font), url(path/to/font.svg) format("svg"),
       url(path/to/font.woff) format("woff"),
       url(path/to/font.otf) format("opentype");
}
```
