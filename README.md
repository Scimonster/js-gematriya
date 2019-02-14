# Gematriya

[Gematriya/Gematria](https://en.wikipedia.org/wiki/Gematria), or perhaps more accurately, [Hebrew numerals](https://en.wikipedia.org/wiki/Hebrew_numerals), is a system of writing numbers as Hebrew letters. This JavaScript module allows for easy conversion between gematriya and JavaScript `Number` types.

This code was originally written for [hebcal/hebcal-js](https://github.com/hebcal/hebcal-js).

## Install

Install gematriya from NPM, bower, or just take the `gematriya.js` script from this repo.

```bash
npm install gematriya
bower install gematriya
```

## API

On the client side, the API is available through the global function `gematriya`. In Node, `require('gematriya')`.

A single function is available. Pass it a `Number` or `String`. Given a number, it will return the string representation. Given a gematriya string, it will return the number it represents.

When passing a string, by default, it just adds up the numbers, regardless of place. By passing `{order: true}` as a second parameter, it will treat it as being ordered, as per the output (see below).

When passing a number, an optional options object is available as a second parameter. Setting a number as a value for the `limit` key will limit the length of the returned string to a number of digits. Setting false as the value for the `punctuate` key will remove double and single quotation marks in the returned string. Setting `geresh` to false will use ASCII single/double quotes instead of Hebrew geresh/gershayim Unicode characters. Like this:

```js
gematriya(5774) // התשע״ד - ordinary
gematriya(5774, {limit: 3}) // תשע״ד - cropped to 774
gematriya(5774, {limit: 7}) // התשע״ד - kept at 5774
gematriya(5774, {punctuate: false}) // 'התשעד' - removed quotation marks
gematriya(5774, {punctuate: true}) // 'התשע״ד' - with quotation marks
gematriya(5774, {geresh: false}) // 'התשע"ד' - with quotation marks
gematriya(5774, {punctuate: false, limit: 3}) // 'תשעד' - options can be combined
gematriya(3) // 'ג׳' - note the geresh is RTL
gematriya(3, {geresh: false}) // - "ג'" - the apostrophe is not
gematriya('התשעד', {order: true}) // 5774 - treats the characters as an ordered number
gematriya('התשעד', {order: false}) // 779 - Adds up all the characters
```

## License

Licensed MIT.
