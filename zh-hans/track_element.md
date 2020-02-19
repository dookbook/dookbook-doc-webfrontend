TOPICS: <track>

# `<track>`

HTML元素`<track>`用作媒体元素[`<audio>`](/zh-hans/webfrontend/<audio>)和[`<video>`](/zh-hans/webfrontend/<video>)的子元素。
它使您可以指定定时的文本轨道（或基于时间的数据），例如以自动处理字幕。轨道以WebVTT格式（.vtt文件）格式化— Web视频文本轨道或定时文本标记语言（TTML）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | 没有 |
| **允许的内容** | 无，这是一个空元素。 |
| **标签遗漏** | 由于它是一个void元素，因此必须存在开始标签，而不能存在结束标签。 |
| **允许的父元素** | 任何流内容之前的媒体元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLTrackElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `default` | 此属性指示应该启用该轨道，除非用户的首选项指示另一个轨道更合适。 每个媒体元素只能在一个`track`元素上使用。 |
| `kind` | 如何使用文本轨道。如果省略，则默认类型为**字幕**。如果该属性不存在，它将使用字幕。如果属性包含无效值，则将使用**元数据**。(低于52的Chrome版本将无效值视为**字幕**。)允许使用以下关键字：<br> **字幕** <br> 1、字幕提供了观看者无法理解的内容翻译。例如，英语电影中的对话或非英语文本。<br> 2、字幕可能包含其他内容，通常是其他背景信息。例如，《星球大战》电影开头的文字或场景的日期，时间和位置。<br> **字幕说明** <br> 1、隐藏式字幕提供了音频的转录和翻译。<br> 2、它可能包含重要的非语言信息，例如音乐提示或声音效果。它可能指示提示的来源（例如音乐，文本，角色）。<br> 3、适用于聋哑或声音被静音的用户。<br> **描述** <br> 1、视频内容的文字描述。<br> 2、适用于盲人或看不到视频的用户。<br> **章节** <br> 1、章节标题旨在在用户浏览媒体资源时使用。<br> **元数据** <br> 1、脚本使用的轨道。对用户不可见。
| `label` | 文本轨道的用户可读标题，浏览器在列出可用的文本轨道时使用. |
| `src` | 轨道的地址（.vtt文件）。 必须是有效的网址。 必须指定此属性，并且其URL值必须与文档具有相同的来源-除非`track`元素的[`<audio>`](/zh-hans/webfrontend/<audio>)或[`<video>`](/zh-hans/webfrontend/<video>)父元素具有`crossorigin`属性。|
| `srclang` | 轨道文本数据的语言。 它必须是有效的BCP 47语言标记。 如果将`kind`属性设置为`subtitles`，则必须定义`srclang`。 |

## 使用说明

“轨道”添加到媒体的数据类型在kind属性中设置，该属性可以采用“字幕”，“字幕”，“描述”，“章节”或“元数据”的值。 元素指向包含定时文本的源文件，当用户请求其他数据时，浏览器将显示该文本。

“媒体”元素不能具有相同的“种类”，`srclang`和`label`相同的`track`。

## 示例

```html
<video controls poster="/images/sample.gif">
   <source src="sample.mp4" type="video/mp4">
   <source src="sample.ogv" type="video/ogv">
   <track kind="captions" src="sampleCaptions.vtt" srclang="en">
   <track kind="descriptions"
     src="sampleDescriptions.vtt" srclang="en">
   <track kind="chapters" src="sampleChapters.vtt" srclang="en">
   <track kind="subtitles" src="sampleSubtitles_de.vtt" srclang="de">
   <track kind="subtitles" src="sampleSubtitles_en.vtt" srclang="en">
   <track kind="subtitles" src="sampleSubtitles_ja.vtt" srclang="ja">
   <track kind="subtitles" src="sampleSubtitles_oz.vtt" srclang="oz">
   <track kind="metadata" src="keyStage1.vtt" srclang="en"
     label="Key Stage 1">
   <track kind="metadata" src="keyStage2.vtt" srclang="en"
     label="Key Stage 2">
   <track kind="metadata" src="keyStage3.vtt" srclang="en"
     label="Key Stage 3">
   <!-- Fallback -->
   ...
</video>
```
