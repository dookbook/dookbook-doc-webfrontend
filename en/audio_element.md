TOPICS: <audio>

# `<audio>`

The **HTML `<audio>` element** is used to embed sound content in documents. It may contain one or
more audio sources, represented using the `src` attribute or the [`<source>`](/en/webfrontend/<source>)
element: the browser will choose the most suitable one.

The above example shows simple usage of the `<audio>` element. In a similar manner
to the [`<img>`](/en/webfrontend/<img>) element, we include a path to the media we want to embed
inside the `src` attribute; we can include other attributes to specify information such as whether
we want it to autoplay and loop, whether we want to show the browser's default audio controls, etc.

The content inside the opening and closing `<audio></audio>` TOPICS is shown as a
fallback in browsers that don't support the element.

You can also use Gecko's more powerful audio API feature to directly generate and control audio
streams in JavaScript code. See [Introducing the audio API extension](https://wiki.developer.mozilla.org/en-US/docs/Introducing_the_Audio_API_Extension)
for details.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content Categories** | Flow Content,Phrasing Content,embedded content. If you have control properties:nteractive content,palpable content. |
| **Permitted content** | If the element contains an `src` attribute: zero or more [`<track>`](/zh-hans/webfrontend/<track>) elements, which cannot immediately follow the transparent content of the `<audio>` or [`<video>`](/zh-hans/webfrontend/<video>) media element. For example: zero or more [`<source>`](/zh-hans/webfrontend/<source>) elements, followed by zero or more `<track>` elements, cannot be followed by transparent content of `<audio>` or [`<video>`](/zh-hans/webfrontend/<video>) media elements. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts embedded content.|
| **Permitted ARIA roles** | `application` |
| **DOM interface** | **`HTMLAudioElement`** |

## Attributes

| Attribute | Description |
| :-- | :-- |
| `autoplay` | A Boolean attribute: if specified, the audio will automatically begin playback as soon as it can do so, without waiting for the entire audio file to finish downloading.<br>**Note:** Sites that automatically play audio (or videos with an audio track) can be an unpleasant<br>experience for users, so should be avoided when possible. If you must offer autoplay functionality,<br>you should make it opt-in (requiring a user to specifically enable it). However, this can be useful<br>when creating media elements whose source will be set at a later time, under user control. |
| `buffered` | You can use this property to get the time period information of the buffered resource. This property contains a `TimeRanges` object.|
| `controls` | If this attribute is present, the browser will offer controls to allow the user to control audio playback, including volume, seeking, and pause/resume playback. |
| `loop` | Boolean property: If specified, the loop audio. |
| `mozCurrentSampleOffset` |A value representing the offset from the beginning of the audio during audio playback. |
| `muted` | A Boolean attribute that indicates whether the audio will be initially silenced. Its default value is `false`. |
| `played` |A `TimeRanges` object that represents all the audio clips that have been played. |
| `preload` | This enumerated attribute is intended to provide a hint to the browser about what the author thinks will lead to the best user experience. It may have one of the following values:<br>`none`: Indicates that the user may not play the audio, or the server wants to save bandwidth; in other words, the audio will not be cached;<br>`metadata`: Signals that even if the user may not play the audio, they will get their metadata (such as audio length) and still have the necessary content.<br>`auto`: Indicates that the whole audio file can be downloaded, even if the user is not expected to use it.<br>empty string: A synonym of the `auto` value.<br>The default value is different for each browser. The spec advises it to be set to `metadata`<br>**Notes:** The autoplay attribute has precedence over preload. If autoplay is specified, the browser<br>would obviously need to start downloading the audio for playback.<br>The browser is not forced by the specification to follow the value of this attribute; it is a mere hint.|
| `crossorigin` | This enumerated attribute indicates whether to use CORS to fetch the related image. CORS-enabled resources can be reused in the `<canvas>` element without being tainted. |
| `currentTime` | Reading `currentTime` returns a double-precision floating-point value indicating the current playback position, in seconds, of the audio. If the audio's metadata isn't available yet—thereby preventing you from knowing the media's start time or duration—`currentTime` instead indicates, and can be used to change, the time at which playback will begin. Otherwise, setting `currentTime` sets the current playback position to the given time and seeks the media to that position if the media is currently loaded.<br>If the audio is being streamed, it's possible that the user agent may not be able to obtain some parts of the resource if that data has expired from the media buffer. Other audio may have a media timeline that doesn't start at 0 seconds, so setting `currentTime` to a time before that would fail. For example, if the audio's media timeline starts at 12 hours, setting `currentTime` to 3600 would be an attempt to set the current playback position well before the beginning of the media, and would fail. The `getStartDate()` method can be used to determine the beginning point of the media timeline's reference frame. |
| `disableRemotePlayback` | A Boolean attribute used to disable the capability of remote playback in devices that are attached using wired (HDMI, DVI, etc.) and wireless technologies (Miracast, Chromecast, DLNA, AirPlay, etc). See this proposed specification for more information.<br>**Note:** In Safari, you can use `x-webkit-airplay="deny"` as a fallback. |
| `duration` | A double-precision floating-point value which indicates the duration (total length) of the audio in seconds, on the media's timeline. If no media is present on the element, or the media is not valid, the returned value is `NaN`. If the media has no known end (such as for live streams of unknown duration, web radio, media incoming from WebRTC, and so forth), this value is `+Infinity`.|
| `src` | The URL of the audio to embed. This is subject to HTTP access controls. This is optional; you may instead use the [`<source>`](/en/webfrontend/<source>) element within the audio block to specify the audio to embed.|
| `volume` |Audio playback volume. Values are from 0.0 (silent) to 1.0 (loudest). The time offset is currently specified as a `float` type value, representing the number of seconds to offset.|

## Usage Notes

Browsers don't all support the same audio formats; you can provide multiple sources inside
nested [`<source>`](/en/webfrontend/<source>) elements, and the browser will then use the
first one it understands.

Other Usage Notes:

- The `autoplay` attribute takes precedence over `preload`. If the user wants to play the video automatically,
then obviously
the browser needs to download the video. Setting both the `autoplay` and `preload` properties is
allowed in the specification.The autoplay attribute takes precedence over preload. If the user wants
to play the video automatically, then obviously the browser needs to download the video. Setting
both the autoplay and preload properties is allowed in the specification.
- If you don't specify the `controls` attribute, the audio player won't include the browser's
default controls.
You can, however,create your own custom controls using JavaScript and the `HTMLMediaElement` API.
- To allow precise control over your audio content, `HTMLMediaElements` fire many different events.
This also provides a way to monitor the audio's fetching process so you can watch for errors or
detect when enough is available to begin to play or manipulate it.
- You can also use the Web Audio API to directly generate and manipulate audio streams from JavaScript
code rather than streaming pre-existing audio files.
- `<audio>` elements can't have subtitles or captions associated with them in the same way that
[`<video>`](/en/webfrontend/<video>) elements can. See [WebVTT and Audio](https://www.iandevlin.com/blog/2015/12/html5/webvtt-and-audio)
by Ian Devlin for some useful information and workarounds.

**Note:**  In the HTML 5 specification, the definition of the time offset value has not yet been completed
 and may change.

## Events

| Event Name | Fired When |
| :-- | :-- |
| `audioprocess` | The input buffer of a `ScriptProcessorNode` is ready to be processed. |
| `canplay` | The browser can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content. |
| `canplaythrough` | The browser estimates it can play the media up to its end without stopping for content buffering.|
| `complete` | The rendering of an `OfflineAudioContext` is terminated.|
| `durationchange` | The `duration` attribute has been updated.|
| `emptied` | The media has become empty; for example, this event is sent if the media has already been loaded (or partially loaded), and the `load()` method is called to reload it.|
| `ended` | Playback has stopped because the end of the media was reached.|
| `loadeddata` | The first frame of the media has finished loading.|
| `loadedmetadata` | The metadata has been loaded.|
| `pause` | Playback has been paused.|
| `play` | Playback has begun. |
| `playing` | Playback is ready to start after having been paused or delayed due to lack of data. |
| `ratechange` | The playback rate has changed.|
| `seeked` | A seek operation completed.|
| `seeking` | A seek operation began.|
| `stalled` | The user agent is trying to fetch media data, but data is unexpectedly not forthcoming.|
| `suspend` | Media data loading has been suspended.|
| `timeupdate` | The time indicated by the `currentTime` attribute has been updated.|
| `volumechange` | The volume has changed.|
| `waiting` | Playback has stopped because of a temporary lack of data.|

### Styling with CSS

The `<audio>` element has no intrinsic visual output of its own unless the `controls` attribute is
specified, in which case the browser's default controls are shown.

The default controls have a `display` value of `inline` by default, and it is often a good
idea set the value to `block` to improve control over positioning and layout,
unless you want it to sit within a text block or similar.

You can style the default controls with properties that affect the block as a single unit,
so for example you can give it a `border` and `border-radius`, `padding`, `margin`, etc.
You can't however style the individual components inside the audio player (e.g. change the button
size or icons, change the font, etc.), and the controls are different across the different browsers.

To get a consistent look and feel across browsers, you'll need to create custom controls; these can
be marked up and styled in whatever way you want, and then JavaScript can be used along with the
`HTMLMediaElement` API to wire up their functionality.

Video player styling basics provides some useful styling techniques — it is written in the
context of [`<video>`](/en/webfrontend/<video>), but much of it is equally applicable to `<audio>`.

### Detecting addition and removal of tracks

You can detect when tracks are added to and removed from an `<audio>` element using the
`addtrack` and `removetrack` events. However, these events aren't sent directly to
the `<audio>` element itself. Instead, they're sent to the track list object within the `<audio>`
element's `HTMLMediaElement` that corresponds to the type of track that was added to the element:

`HTMLMediaElement.audioTracks`

An `AudioTrackList` containing all of the media element's audio tracks. You can add a
listener for `addtrack` to this object to be alerted when new audio tracks are added to the element.

`HTMLMediaElement.videoTracks`

Add an `addtrack` listener to this `VideoTrackList` object to be informed when
video tracks are added to the element.

`HTMLElement.textTracks`

Add an `addtrack` event listener to this `TextTrackList` to be notified when new
text tracks are added to the element.

!!! warn "Don't try this at home"
    Note: Even though it's an `<audio>` element, it still has video and text track lists, and can in
    fact be used to present video, although the use interface implications can be odd.

For example, to detect when audio tracks are added to or removed from an `<audio>` element,
you can use code like this:

```javascript
var elem = document.querySelector("audio");

elem.audioTrackList.onaddtrack = function(event) {
  trackEditor.addTrack(event.track);
};

elem.audioTrackList.onremovetrack = function(event) {
  trackEditor.removeTrack(event.track);
};
```

This code watches for audio tracks to be added to and removed from the element, and calls a
hypothetical function on a track editor to register and remove the track from the editor's
list of available tracks.

You can also use `addEventListener()` to listen for the
`addtrack` and `removetrack` events.

## Examples

### Basic Usage

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

The following example shows simple usage of the `<audio>` element to play an OGG file. It will
autoplay due to the `autoplay` attribute, and also includes fallback content.

```html
<!-- Simple audio playback -->
<audio
  src="AudioTest.ogg"
  autoplay>
  Your browser does not support the <code>audio</code> element.
</audio>
```

### `<audio>` element with `<source>` element

This example specifies which audio track to embed using the `src` attribute on a nested
[`<source>`](/en/webfrontend/<source>) element rather than directly on the `<audio>` element. It is
always useful to include the file's MIME type inside the `type` attribute, as the browser is able to
instantly tell if it can play that file, and not waste time on it if not.

```html
<audio controls="controls">
  <source src="foo.wav" type="audio/wav">
  Your browser does not support the <code>audio</code> element.
</audio>
```

### `<audio>` with multiple `<source>` elements

This example includes multiple [`<source>`](/en/webfrontend/<source>) elements. The browser tries to
load the first source element (Opus) if it is able to play it; if not it falls back to the second
(Vorbis) and finally back to MP3:

```html
<audio controls="">
 <source src="foo.opus" type="audio/ogg; codecs=opus"/>
 <source src="foo.ogg" type="audio/ogg; codecs=vorbis"/>
 <source src="foo.mp3" type="audio/mpeg"/>
</audio>
```

## Accessibility Concerns

Audio with spoken dialog should provide both captions and transcripts that accurately describe its
content. Captions, which are specified using WebVTT, allow people who are experiencing hearing loss
to understand an audio recording's content as the recording is being played, while transcripts allow
people who need additional time to be able to review the recording's content at a pace and format
that is comfortable for them.

If automatic captioning services are used, it is important to review the generated content to ensure
it accurately represents the source audio.

The `<audio>` element doesn't directly support WebVTT. You will have to find a library or framework
that provides the capability for you, or write the code to display captions yourself.

In addition to spoken dialog, subtitles and transcripts should also identify music and sound effects
that communicate important information. This includes emotion and tone. For example, in the WebVTT
below, note the use of square brackets to provide tone and emotional insight to the viewer;
this can help establish the mood otherwise provided using music, nonverbal sounds and crucial
sound effects, and so forth.

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

Also it's a good practice to provide some content (such as the direct download link) as a fallback
for viewers who use a browser in which the `<audio>` element is not supported:

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
