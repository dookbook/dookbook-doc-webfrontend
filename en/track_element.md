TOPICS: <track>

# `<track>`

The **HTML `<track>` element** is used as a child of the media elements [`<audio>`](/en/webfrontend/<audio>)
and [`<video>`](/en/webfrontend/<video>). It lets you specify timed text tracks (or time-based data),
for example to automatically handle subtitles. The tracks are formatted in WebVTT format
(.vtt files) — Web Video Text Tracks or Timed Text Markup Language (TTML).

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | None |
| **Permitted content** | None, it is an empty element. |
| **Tag omission** | As it is a void element, the start tag must be present and the end tag must not be present. |
| **Permitted parents** | A media element, before any *flow content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLTrackElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `default` | This attribute indicates that the track should be enabled unless the user's preferences indicate that another track is more appropriate. This may only be used on one `track` element per media element. |
| `kind` | How the text track is meant to be used. If omitted the default kind is `subtitles`. If the attribute is not present, it will use the `subtitles`. If the attribute contains an invalid value, it will use `metadata`. (Versions of Chrome earlier than 52 treated an invalid value as `subtitles`.) The following keywords are allowed:<br>**`subtitles`**<br>1. Subtitles provide translation of content that cannot be understood by the viewer. For example dialogue or text that is not English in an English language film.<br>2. Subtitles may contain additional content, usually extra background information. For example the text at the beginning of the Star Wars films, or the date, time, and location of a scene.<br>**`captions`**<br>1. Closed captions provide a transcription and possibly a translation of audio.<br>2. It may include important non-verbal information such as music cues or sound effects. It may indicate the cue's source (e.g. music, text, character).<br>3. Suitable for users who are deaf or when the sound is muted.<br>**`descriptions`**<br>1. Textual description of the video content.<br>2. Suitable for users who are blind or where the video cannot be seen.<br>**`chapters`**<br>1. Chapter titles are intended to be used when the user is navigating the media resource.<br>**`metadata`**<br>1. Tracks used by scripts. Not visible to the user.<br><br>The type of data that `track` adds to the media is set in the kind attribute, which can take values of `subtitles`, `captions`, `descriptions`, `chapters` or `metadata`. The element points to a source file containing timed text that the browser exposes when the user requests additional data.|
| `label` | A user-readable title of the text track which is used by the browser when listing available text tracks. |
| `src` | Address of the track (`.vtt` file). Must be a valid URL. This attribute must be specified and its URL value must have the same origin as the document — unless the [`<audio>`](/en/webfrontend/<audio>) or [`<video>`](/en/webfrontend/<video>) parent element of the `track` element has a `crossorigin` attribute. |
| `srclang` | Language of the track text data. It must be a valid BCP 47 language tag. If the `kind` attribute is set to `subtitles`, then `srclang` must be defined. |

## Usage Notes

A `media` element cannot have more than one `track` with the same `kind`, `srclang`, and `label`.

## Examples

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

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
|  `<track>` | support | support | support |
