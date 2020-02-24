TOPICS: word-break property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `word-break`

The **`word-break`** CSS property specifies **how to break lines within a word**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Use the default line break rule. |
| **`break-all`** | To prevent overflow, word breaks should be inserted between any two characters (excluding Chinese/Japanese/Korean text). |
| **`keep-all`** | Word breaks should not be used for Chinese/Japanese/Korean (CJK) text. Non-CJK text behavior is the same as for `normal`. |

## Examples

```css
.narrow {
  padding: 10px;
  border: 1px solid;
  width: 500px;
  margin: 0 auto;
  font-size: 20px;
  line-height: 1.5;
  letter-spacing: 1px;
}

.normal {
  word-break: normal;
}

.breakAll {
  word-break: break-all;
}

.keepAll {
  word-break: keep-all;
}

.breakWord {
  word-break: break-word;
}
```

```html
<p>1. <code>word-break: normal</code></p>
<p class="normal narrow">This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

<p>2. <code>word-break: break-all</code></p>
<p class="breakAll narrow">This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

<p>3. <code>word-break: keep-all</code></p>
<p class="keepAll narrow">This is a long and
 Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>

<p>4. <code>word-break: break-word</code></p>
<p class="breakWord narrow">This is a long and
  Honorificabilitudinitatibus califragilisticexpialidocious Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
 グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉</p>
```
