TOPICS: word-break property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         庄引; zhuangyin8@gmail.com; github:zhuangyin8
         Teoli; teoli@mozilla.net; mdn:teoli
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Ivan Yan; yanxyz@github.com; github:yanxyz

# CSS 属性: `word-break`

CSS 属性 **`word-break`** 指定了**怎样在单词内断行**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 使用默认的断行规则。|
| **`break-all`** | 对于`non-CJK` (CJK 指中文/日文/韩文) 文本，可在任意字符间断行。|
| **`keep-all`** | CJK 文本不断行。 Non-CJK 文本表现同 `normal`。|

## 示例

```css
.narrow {
  padding: 5px;
  border: 1px solid;
  display: table;
  max-width: 100%;
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
