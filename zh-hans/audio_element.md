TOPICS: <audio>

# `<audio>`

HTML `<audio>` 元素用于在文档中表示音频内容。 `<audio>` 元素可以包含一个或多个音频资源， 这些音频资源可以使用 `src` 属性或者
[`<source>`](/zh-hans/webfrontend/<source>) 元素来进行描述； 浏览器将会选择最合适的一个来使用。

`<audio>`元素与`<img>`元素的方式类似，我们可以在`src`属性中嵌入了一个媒体路径;也可以包含其他属性来指定信息，例如：是否希望它自动播放、循环、是否在浏览器中显示为默认音频控件等等。

可以在 `<audio>` 和 `</audio>` 之间放置文本内容，这些文本信息将会被显示在那些不支持 `<audio>`标签的浏览器中。

你也可以使用Gecko特有的更加强大的audio API特性在JavaScript 代码中直接生成和控制音频流。详情参见 [Introducing the audio API extension](https://wiki.developer.mozilla.org/en-US/docs/Introducing_the_Audio_API_Extension)

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*嵌入内容*。 如果具有控件属性：*交互式内容*和*可触摸的内容*。 |
| **允许内容** | 如果元素包含 `src` 属性：零个或多个 [`<track>`](/zh-hans/webfrontend/<track>) 元素，其后不能紧跟 `<audio>` 或者 [`<video>`](/zh-hans/webfrontend/<video>)媒体元素的透明内容。如：零个或多个 [`<source>`](/zh-hans/webfrontend/<source>) 元素，其后紧跟零个或多个 [`<track>`](/zh-hans/webfrontend/<track>) 元素，则其后不能紧跟 `<audio>` 或者 [`<video>`](/zh-hans/webfrontend/<video>)媒体元素的透明内容。 |
| **标记省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父级元素** | 任何接受嵌入内容的元素。|
| **允许的 ARIA 角色** | `application` |
| **DOM 接口** | **`HTMLAudioElement`** |

## 属性

该元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `autoplay` | 布尔属性：如果指定（默认值为"false"！）；指定后，则音频将自动开始播放，而无需等待整个音频文件完成下载。<br> **注意**：自动播放音频（或带有音轨的视频）的网站可能会给用户带来不愉快的体验，因此应尽可能避免使用。如果必须提供自动播放功能，则应启用它（要求用户专门启用它）。但是，这在创建媒体元素时很有用，该媒体元素的来源将在以后由用户控制。 |
| `buffered` | 你可以通过该属性获取已缓冲的资源的时间段信息。该属性包含一个 `TimeRanges` 对象。 |
| `controls` | 如果设置了该属性，浏览器将提供一个包含声音、播放进度、播放暂停的控制面板，让用户可以控制音频的播放。 |
| `loop` | 布尔属性：如果指定，将循环播放音频。 |
| `mozCurrentSampleOffset` | 在音频播放时，表示相对于音频开始处的偏移量的一个数值。 |
| `muted` | 表示是是否静音的布尔值。默认值为false，表示有声音。 |
| `played` | 一个TimeRanges 对象，表示所有已播放的音频片段。 |
| `preload` | 枚举属性，让开发者自行思考来示意浏览器使用何种加载方式以达到最好的用户体验。可以是以下属性之一：<br>`none`: 示意用户可能不会播放该音频，或者服务器希望节省带宽；换句话说，该音频不会被缓存；<br>`metadata`: 示意即使用户可能不会播放该音频，但会获取其元数据 (例如音频长度) 还有必要的内容。<br>`auto`: 示意用户可能会播放音频；换句话说，如果有必要，整个音频都将被加载，即使用户不期望使用。<br>空字符串 : 等效于`auto`属性。<br>每个浏览器的默认值都不同。规范建议将其设置为`metadata`。<br> **注意：** `autoplay`属性的优先级高于预加载。如果指定了自动播放，则浏览器显然需要开始下载音频以进行播放。<br>不强制规范的浏览器遵循该属性的值；（这仅仅是一个提示。） |
| `crossorigin` |此枚举的属性指示是否使用CORS来获取相关图像。启用CORS的资源可以在`<canvas>`元素中重用而不会受到污染。|
| `currentTime` |读取`currentTime`将返回一个双精度浮点值，该值指示音频的当前播放位置（以秒为单位）。<br>如果音频的元数据尚不可用（从而使您无法知道媒体的开始时间或持续时间)`currentTime`则表示并可以用来更改播放的开始时间。否则，设置`currentTime`会将当前播放位置设置为给定时间，如果当前正在加载媒体，则将媒体搜索到该位置。<br>如果正在传输音频，则如果媒体缓冲区中的数据已过期，则用户代理可能无法获取资源的某些部分。其他音频的媒体时间轴可能不是从0秒开始的，因此请设置`currentTime`到失败的时间。例如，如果音频的媒体时间轴从12小时开始，则设置`currentTime`为3600会试图在媒体开始之前就设置当前播放位置，并且会失败。该getStartDate()方法可用于确定媒体时间轴参考帧的起点。|
| `disableRemotePlayback` | 一个布尔属性，用于禁用使用有线（HDMI，DVI等）和无线技术（Miracast，Chromecast，DLNA，AirPlay等）连接的设备中的远程播放功能。有关更多信息，请参见此建议的规范。<br> **注意：**在`Safari`中，您可以将其`x-webkit-airplay="deny"`用作备用。|
| `duration` | 一个双精度浮点值，它指示媒体时间线上音频的持续时间（总长度），以秒为单位。如果元素上没有任何介质，或者介质无效，则返回值为`NaN`。如果媒体没有已知的结尾（例如，持续时间未知的实时流，网络广播，从WebRTC传入的媒体等），则此值为`+Infinity`。|
| `src` | 要嵌入的音频的URL。这受HTTP访问控制。这是可选的,您可以改为使用`<source>`音频块中的元素来指​​定要嵌入的音频。|
| `volume` | 音频播放的音量。值从0.0 (无声) 到 1.0 (最大声) 时间偏移量目前是指定为`float`类型的值。表示偏移的秒数。|

## 使用说明

 浏览器并不都支持相同的音频格式。您可以在嵌套`<source>`元素中提供多个元素，然后浏览器将使用它理解的第一个元素。

 其他用法说明：

- `autoplay` 属性优先于 `preload`, 假如用户想自动播放视频，那么很明显浏览器需要下载视频。同时设置`autoplay` 和 `preload`属性在规范里是允许的。规范没有强制浏览器去遵循该属性的值；这仅仅只是个提示。
- 如果您未指定`controls`属性，则音频播放器将不包含浏览器的默认控件。但是，您可以使用JavaScript和`HTMLMediaElementAPI` 创建自己的自定义控件。
- 为了精确控制音频内容，用`HTMLMediaElements`可触发许多不同的事件。这也提供了一种监视音频获取过程的方法，因此您可以在检查错误或检测时,有足够的可用空间来开始播放或操纵它。
- 您还可以使用`Web Audio API`直接从JavaScript代码生成和处理音频流，而不是使用流式传输预先存在的音频文件。
- `<audio>`元素不能像`<video>`元素一样具有与其相关联的字幕。其他有关的信息和解决方法，请参见I[WebVTT and Audio](https://www.iandevlin.com/blog/2015/12/html5/webvtt-and-audio)和音频。
  
**备注**： HTML 5 规范中，时间偏移量值的定义还没有完成，有可能会变更。

## 事件

`audio`元素支持的事件

| 名 称 | 触发时间 |
| :-- | :-- |
| `audioprocess` | 可以处理`ScriptProcessorNode`的输入缓冲区。|
| `canplay` | 浏览器可以播放音频，但当没有足够的数据被加载时,音频会一直播放到它的结束，而不必停下来进行缓冲内容。|
| `canplaythrough` | 浏览器可以播放媒体到最后，而无需停止内容缓冲。|
| `complete` | `OfflineAudioContext`的播放到结尾。|
| `durationchange` | 表示`duration`属性已更新。|
| `emptied` | 表示音频已经空了；例如:如果已加载（或部分加载）的音频，则发送此事件，并用`load()`方法重新加载它。|
| `ended` | 由于已到达音频结尾，因此播放已停止。|
| `loadeddata` | 音频的第一帧已完成加载。|
| `loadedmetadata` | 数据已加载。|
| `pause` | 播放已暂停。|
| `play` | 播放已经开始。|
| `playing` | 播放开始后，由于缺乏数据已暂停或延迟。|
| `ratechange` | 更改播放速度。|
| `seeked` | 搜索操作完成。|
| `seeking` | 开始搜索操作。|
| `stalled` | 用户代理正在尝试获取音频数据，但是数据出乎意料地没能得到。|
| `suspend` | 音频数据加载已暂停。|
| `timeupdate` | `currentTime`属性表示时间已更新。|
| `volumechange` | 音量已更改。|
| `waiting` | 由于暂时缺少数据，播放已停止。|

## 示例

### 基本用法

```html
<!-- Simple audio playback -->
<audio src="http://developer.mozilla.org/@api/deki/files/2926/=AudioTest_(1).ogg" autoplay>
  Your browser does not support the <code>audio</code> element.
</audio>

<!-- Audio playback with captions -->
<audio src="foo.ogg">
  <track kind="captions" src="foo.en.vtt" srclang="en" label="English">
  <track kind="captions" src="foo.sv.vtt" srclang="sv" label="Svenska">
</audio>
```

下面的示例演示该`<audio>`元素播放OGG文件的简单用法。由于该autoplay属性，它将自动播放，并且还包括备用内容。

```html
<!-- Simple audio playback -->
<audio
  src="AudioTest.ogg"
  autoplay>
  Your browser does not support the <code>audio</code> element.
</audio>
```

### 使用`source`元素的`audio`元素

本示例使用`src`属性在嵌套 `<source>`元素上,而不是直接在`<audio>`元素上指定要嵌入的音轨。将文件的MIME类型包含在`type`属性中总是有用的，因而浏览器能够立即判断它是否可以播放该文件，并且如果不可以，则避免浪费时间。

```html
<audio controls="controls">
  Your browser does not support the <code>audio</code> element.
  <source src="foo.wav" type="audio/wav">
</audio>
```

### `<audio>`具有多个`<source>`元素

此示例包括多个`<source>`元素。如果能够播放，则浏览器尝试加载第一个元素（`Opus`）。如果不是，它跳到第二个（`Vorbis`），最后回到MP3：

```html
<audio controls="">
 <source src="foo.opus" type="audio/ogg; codecs=opus"/>
 <source src="foo.ogg" type="audio/ogg; codecs=vorbis"/>
 <source src="foo.mp3" type="audio/mpeg"/>
</audio>
```

## 可访问性问题

语音对话应该提供准确描述其内容的字幕和文字记录,以准确描述其内容。 使用WebVTT指定的字幕可让正在听力受损的人在播放录音时了解录音的内容，而笔录则使需要更多时间处理,才能够以一定的节奏和格式查看录音的内容对他们来说很舒服。

如果使用自动字幕，则查看生成的内容以确保其准确表示源音频。

该`<audio>`元素不直接支持WebVTT。您将必须找到一个库或框架来为您提供此此功能，或者编写代码来自己显示字幕。

除口语对话外，字幕和文字记录还应标识传达重要信息的音乐和声音效果,这包括情绪和语气。例如，在下面的WebVTT中，请注意使用方括号为观看者提供声调和情感洞察力；这可以使用音乐，非语言声音和重要声音效果等提供的情绪。

```http
1
00:00:00 --> 00:00:45
Energetic techno music]

2
00:00:46 --> 00:00:51
Welcome to the Time Keeper's podcast! In this episode we're discussing which Swisswatch is a wrist switchwatch?

16
00:00:52 --> 00:01:02
Laughing] Sorry! I mean, which wristwatch is a Swiss wristwatch?
```

另外，对于使用不支持`<audio>`元素的浏览器，可以为其提供一些其他内容（例如直接下载链接）作为备用也是一种好习惯：

```html
<audio controls>
  <source src="myAudio.mp3" type="audio/mpeg">
  <source src="myAudio.ogg" type="audio/ogg">
  <p>
    Your browser doesn't support HTML5 audio.
    Here is a <a href="myAudio.mp4">link to download the audio</a> instead.
  </p>
</audio>
```

- [MDN Subtitles and closed caption — Plugins](https://wiki.developer.mozilla.org/en-US/docs/Plugins/Flash_to_HTML5/Video/Subtitles_captions)
- [Web Video Text Tracks Format (WebVTT)](https://wiki.developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [WebAIM: Captions, Transcripts, and Audio Descriptions](https://webaim.org/techniques/captions/)
- [MDN Understanding WCAG, Guideline 1.2 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#Guideline_1.2_%E2%80%94_Providing_text_alternatives_for_time-based_media)
- [Understanding Success Criterion 1.2.1 | W3C Understanding WCAG 2.0](https://www.w3.orgTR/UNDERSTANDING-WCAG20/media-equiv-av-only-alt.html)
- [Understanding Success Criterion 1.2.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/media-equiv-captions.html)
