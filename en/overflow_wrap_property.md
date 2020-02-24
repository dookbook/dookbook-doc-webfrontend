TOPICS: overflow-wrap property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `overflow-wrap`

The **`overflow-wrap`** CSS property applies to inline elements, setting **whether the browser should
insert line breaks within an otherwise unbreakable string to prevent text from overflowing its line box**.

!!! warn "Note"
    In contrast to [`word-break`](/en/webfrontend/word-break_property), `overflow-wrap` will
    only create a break if an entire word cannot be placed on its own line without overflowing.

The property was originally a nonstandard and unprefixed Microsoft extension called `word-wrap`, and
was implemented by most browsers with the same name. It has since been renamed to `overflow-wrap`,
with `word-wrap` being an alias.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Lines may only break at normal word break points (such as a space between two words). |
| **`break-word`** | The same as the anywhere value, with normally unbreakable words allowed to be broken at arbitrary points if there are no otherwise acceptable break points in the line, but soft wrap opportunities introduced by the word break are NOT considered when calculating min-content intrinsic sizes. |

## Examples

This example compares the results of `overflow-wrap`, `word-break`, and `hyphens` when breaking
up a long word.

```css
p {
   width: 13em;
   margin: 2px;
   background: gold;
}

.ow-anywhere {
   overflow-wrap: anywhere;
}

.ow-break-word {
   overflow-wrap: break-word;
}

.word-break {
   word-break: break-all;
}

.hyphens {
   hyphens: auto;
}
```

```html
<p>They say the fishing is excellent at
  Lake <em class="normal">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>normal</code>)</p>
<p>They say the fishing is excellent at
  Lake <em class="ow-anywhere">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: anywhere</code>)</p>
<p>They say the fishing is excellent at
  Lake <em class="ow-break-word">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>overflow-wrap: break-word</code>)</p>
<p>They say the fishing is excellent at
  Lake <em class="word-break">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>word-break</code>)</p>
<p>They say the fishing is excellent at
  Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>hyphens</code>, without <code>lang</code> attribute)</p>
<p lang="en">They say the fishing is excellent at
  Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>hyphens</code>, English rules)</p>
<p class="hyphens" lang="de">They say the fishing is excellent at
  Lake <em class="hyphens">Chargoggagoggmanchauggagoggchaubunagungamaugg</em>,
  though I've never been there myself. (<code>hyphens</code>, German rules)</p>
```
