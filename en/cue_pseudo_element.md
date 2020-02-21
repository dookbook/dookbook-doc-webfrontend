TOPICS: ::cue
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Element: `::cue`

The **`::cue`** CSS pseudo-element **matches WebVTT cues within a selected element**. This can be used
to style captions and other cues in media with VTT tracks.

## Permitted properties

Rules with `::cue` in their selectors are limited to using only CSS properties from the following list:

- `background` and its longhand properties
- `color`
- `font` and its longhand properties
- `line-height`
- `opacity`
- `outline` and its longhand properties
- `ruby-position`
- `text-combine-upright`
- `text-decoration` and its longhand properties
- `text-shadow`
- `visibility`
- `white-space`

The properties are applied to the entire set of cues as if they were a single unit. The only
exception is that `background` and its shorthand properties apply to each cue individually, to
avoid creating boxes and obscuring unexpectedly large areas of the media.

## Example

The following CSS sets the cue style so that the text is white and the background is a
translucent black box.

```css
::cue {
  color: #fff;
  background-color: rgba(0, 0, 0, 0.6);
}
```
