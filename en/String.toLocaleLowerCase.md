TOPICS: String.toLocaleLowerCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toLocaleLowerCase()`

The **`toLocaleLowerCase()`** method returns the calling string value converted to lower case,
according to any locale-specific case mappings.

## Syntax

```javascript
str.toLocaleLowerCase()
str.toLocaleLowerCase(locale)
str.toLocaleLowerCase([locale, locale, ...])
```

| parameter | Description |
| :-- | :-- |
| `locale` Optional | The locale parameter indicates the locale to be used to convert to lower case according to any locale-specific case mappings. If multiple locales are given in an [`Array`](/en/webfrontend/Array), the [best available locale](https://tc39.github.io/ecma402/#sec-bestavailablelocale) is used. The default locale is the host environment’s current locale. |

**Return value**: A new string representing the calling string converted to lower case, according
to any locale-specific case mappings.

### Exceptions

- A `RangeError` ("invalid language tag: xx_yy") is thrown if a `locale` argument isn't a valid
language tag.
- A `TypeError` ("invalid element in locales argument") is thrown if an array element isn't of type string.

## Description

This method returns a string and not a [`String`](/en/webfrontend/String) object.

The `toLocaleLowerCase()` method returns the value of the string converted to lower case according
to any locale-specific case mappings. `toLocaleLowerCase()` does not affect the value of the string
itself. In most cases, this will produce the same result as [`toLowerCase()`](/en/webfrontend/String.toLowerCase),
but for some locales, such as Turkish, whose case mappings do not follow the default case mappings
in Unicode, there may be a different result.

## Examples

### Using `toLocaleLowerCase()`

```javascript
'ALPHABET'.toLocaleLowerCase(); // 'alphabet'

'\u0130'.toLocaleLowerCase('tr') === 'i';    // true
'\u0130'.toLocaleLowerCase('en-US') === 'i'; // false

let locales = ['tr', 'TR', 'tr-TR', 'tr-u-co-search', 'tr-x-turkish'];
'\u0130'.toLocaleLowerCase(locales) === 'i'; // true
```
