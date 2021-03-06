TOPICS: Date.toString
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Date.toString()`

The **`toString()`** method returns a string representing the specified
[`Date`](/en/webfrontend/Date) object.

## Syntax

```javascript
dateObj.toString()
```

**parameter**: No parameters

**Return value**: String

## Description

[`Date`](/en/webfrontend/Date) instances inherit their `toString()` method from [`Date.prototype`](/en/webfrontend/Date),
not [`Object.prototype`](/en/webfrontend/Object). `Date.toString()` returns a string
representation of the Date in the format specified in ECMA-262 which can be summarised as:

- Week day: 3 letter English week day name, e.g. "Sat"
- space
- Month name: 3 letter English month name, e.g. "Sep"
- space
- Date: 2 digit day in month, e.g. "01"
- space
- Year: 4 digit year, e.g. "2018"
- space
- Hour: 2 digit hour of day, e.g. "14"
- colon
- Minute: 2 digit minute of hour, e.g. "53"
- colon
- Second: 2 digit second of minute, e.g. "26"
- space
- The string "GMT"
- Timezone offset sign, either:
    - "`+`" for positive offsets (0 or greater)
    - "`-`" for negative offsets (less than zero)
- Two digit hour offset, e.g. "14"
- Two digit minute offset, e.g. "00"
- Optionally, a timezone name consisting of:
    - space
    - Left bracket, i.e. "("
    - An implementation dependent string representation of the timezone, which might be an
      abbreviation or full name (there is no standard for names or abbreviations of timezones),
      e.g. "Line Islands Time" or "LINT"
    - Right bracket, i.e. ")"

E.g. "Sat Sep 01 2018 14:53:26 GMT+1400 (LINT)"

Until ECMAScript 2018 (edition 9), the format of the string returned by `Date.toString` was
implementation dependent. Therefore it should not be relied upon to be in the specified format.

The `toString()` method is automatically called when a date is to be represented as a text value, e.g.
`console.log(new Date()`), or when a date is used in a string concatenation, such as
`var today = 'Today is ' + new Date()`.

`toString()` is a generic method, it does not require that its `this` is a [`Date`](/en/webfrontend/Date)
instance. However, it must have an internal `[[TimeValue]]` property that can't be constructed
using native JavaScript, so it's effectively limited to use with [`Date`](/en/webfrontend/Date)
instances. If called on a non–Date instance, a `TypeError` is thrown.

## Examples

### Using `toString()`

The following assigns the `toString()` value of a [`Date`](/en/webfrontend/Date) object to `myVar`:

```javascript
var x = new Date();
var myVar = x.toString(); // assigns a string value to myVar in the same format as:
                          // Mon Sep 08 1998 14:36:22 GMT-0700 (PDT)
```
