TOPICS: String.toLocaleUpperCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toLocaleUpperCase()`

The **`toLocaleUpperCase()`** method returns the calling string value converted to upper case,
according to any locale-specific case mappings.

## Syntax

```javascript
str.toLocaleUpperCase()
str.toLocaleUpperCase(locale)
str.toLocaleUpperCase([locale, locale, ...])
```

| parameter | Description |
| :-- | :-- |
| `locale` Optional | The locale parameter indicates the locale to be used to convert to upper case according to any locale-specific case mappings. If multiple locales are given in an [`Array`](/en/webfrontend/Array), the [best available locale](https://tc39.github.io/ecma402/#sec-bestavailablelocale) is used. The default locale is the host environment’s current locale. |

**Return value**: A new string representing the calling string converted to upper case, according
to any locale-specific case mappings.

### Exceptions

- A `RangeError` ("invalid language tag: xx_yy") is thrown if a `locale` argument isn't a valid
language tag.
- A `TypeError` ("invalid element in locales argument") is thrown if an array element isn't of type string.

## Description

This method returns a string and not a [`String`](/en/webfrontend/String) object.

The `toLocaleUpperCase()` method returns the value of the string converted to upper case according
to any locale-specific case mappings. `toLocaleUpperCase()` does not affect the value of the string
itself. In most cases, this will produce the same result as [`toUpperCase()`](/en/webfrontend/String.toUpperCase),
but for some locales, such as Turkish, whose case mappings do not follow the default case mappings
in Unicode, there may be a different result.

Also notice that conversion is not necessarily a 1:1 character mapping, as some characters might
result in two (or even more) characters when transformed to upper-case. Therefore the length of the
result string can differ from the input length. This also implies that the conversion is not stable,
so i.E. the following can return `false`:
`x.toLocaleLowerCase() === x.toLocaleUpperCase().toLocaleLowerCase()`

## Examples

### Using `toLocaleUpperCase()`

```javascript
'alphabet'.toLocaleUpperCase(); // 'ALPHABET'

'Gesäß'.toLocaleUpperCase(); // 'GESÄSS'

'i\u0307'.toLocaleUpperCase('lt-LT'); // 'I'

let locales = ['lt', 'LT', 'lt-LT', 'lt-u-co-phonebk', 'lt-x-lietuva'];
'i\u0307'.toLocaleUpperCase(locales); // 'I'
```
