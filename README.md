# hypermd-emojione

In HyperMD, Use [emojione][] to lookup and display emoji `:smile:` :smile:

[Demo](https://hypermd.github.io/hypermd-emojione/example/) | [GitHub](https://github.com/HyperMD/hypermd-emojione) | [![NPM version](https://img.shields.io/npm/v/hypermd-emojione.svg?style=flat-square)](https://npmjs.org/package/hypermd-emojione)


> ⚠️ **License**
>
> Please follow https://www.emojione.com/licenses/free if you use this powerpack.
> 使用前请注意阅读 EmojiOne 使用许可

## How to use

1. install `emojione` and `hypermd-emojione`
2. `import` before creating HyperMD editor
3. create HyperMD editor

### For webpack / parcel

Install the packages: `npm install --save hypermd-emojione emojione`

```js
import * as HyperMD from "hypermd"
import "hypermd-emojione"

const your_textarea = document.getElementById('input-box')
const editor = HyperMD.fromTextArea(your_textarea)
```

### For requirejs (example)

In your HTML:

```html
<textarea id="input-box" cols="30" rows="10"># Emoji X emojione :tada:</textarea>

<script src="https://cdn.jsdelivr.net/npm/requirejs/require.js"></script> <!-- 👈 RequireJS -->
<script src="https://cdn.jsdelivr.net/npm/hypermd/goods/patch-requirejs.js"></script> <!-- 👈 IMPORTANT -->
<script data-main src="main.js"></script>
```

In your JavaScript, before defining your main entry, don't forget :

```js
requirejs.config({
  packages: [
    { name: 'hypermd-emojione', main: 'index.js' },
    { name: 'emojione', main: 'lib/js/emojione.min.js' },
  ]
})
```

Finally, here is [an example of `main.js`](./example/requirejs-main.js) and [a live demo](https://hypermd.github.io/hypermd-emojione/example/).

### For Plain Browser Env

*Why hurting yourself? The bundlers and module loaders are the future!*

See the source of [example file](./example/pbe-index.html). Basically, all you need is adding few lines after CodeMirror and HyperMD, before creating your editor:

```html
<script src='https://cdn.jsdelivr.net/npm/emojione@4/lib/js/emojione.min.js'></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/emojione@4/extras/css/emojione.min.css">
<script src="https://cdn.jsdelivr.net/npm/hypermd-emojione/index.js"></script>
```


## Develop

0. (if needed) update `pbe.manifest.json` and define modules' global var name
1. `npm run dev`
2. Start test. You have to refresh the page manually...


[emojione]: https://www.emojione.com/
