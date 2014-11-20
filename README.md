# Gematriya

[Gematriya/Gematria](https://en.wikipedia.org/wiki/Gematria), or perhaps more accurately, [Hebrew numerals](https://en.wikipedia.org/wiki/Hebrew_numerals), is a system of writing numbers as Hebrew letters. This JavaScript module allows for easy conversion between gematriya and JavaScript `Number` types.

This code was originally written for [hebcal/hebcal-js](https://github.com/hebcal/hebcal-js).

## Install

Install gematriya from NPM, bower, or just take the `gematriya.js` script from this repo.

```
npm install gematriya
bower install gematriya
```

## API

On the client side, the API is available through the global function `gematriya`. In Node, `require('gematriya')`.

A single function is available. Pass it a `Number` or `String`. Given a number, it will return the string representation. Given a gematriya string, it will return the number it represents.

When passing a string, by default, it just adds up the numbers, regardless of place. By passing `true` as a second parameter, it will treat it as being ordered, as per the output (see below).

When passing a number, a second parameter is available, `limit`. This will limit the length of the returned string to a number of digits. For example:

```js
gematriya(5774) // התשע"ד - ordinary
gematriya(5774, 3) // תשע"ד - cropped to 774
gematriya(5774, 7) // התשע"ד - kept at 5774
```

## License

Licensed MIT.
