# ndconvert

A CLI tool for converting images (PNG) to ndarray json files.

Basically it is
[this script](https://github.com/mikolalysenko/isabella-texture-pack/blob/master/convert.js)
copied and turned into a binary to run anywhere.

## example

You have an image `./terrain.png`. Convert it with
`ndconvert terrain.png > terrain.json`. Then in your module use it with:

```js
var decodeBase64 = require('base64-js').toByteArray
var ndarray = require('ndarray')

var terrain = require('./terrain.json')
var texture = ndarray(
  new Uint8Array(decodeBase64(terrain.data)),
  terrain.shape,
  terrain.stride,
  terrain.offset
)
```

## install

With [npm](https://npmjs.org) do:

```
npm install ndconvert -g
```

## release history
* 0.1.0 - initial release
