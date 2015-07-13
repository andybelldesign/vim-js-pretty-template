# vim-js-pretty-template

A Vim plgin to apply other filetype's syntax to JavaScript [Template Strings](http://tc39wiki.calculist.org/es6/template-strings/).

This plugin highlights ES6 Template Strings with other filetype's syntax rule which you want.

```js
var template = `
  <!-- highlighted in HTML's way -->
  <html>
    <body id="main"></body>
  </html>
`;
```

Template Strings is available with [Babel](https://babeljs.io/), [google/traceur-compile](https://github.com/google/traceur-compiler) and [TypeScript](http://www.typescriptlang.org/).

## How to install 

### Vundle

Place this in your `.vimrc`:

```vim
Plugin 'Quramy/vim-js-pretty-template'
```

then run the following in Vim:

```vim
:source %
:PluginInstall
```

### NeoBundle

```vim
NeoBundle 'Quramy/vim-js-pretty-template'
```

then run the following in Vim:

```vim
:source %
:NeoBundleInstall
```

### Pathogen
Run the following in a terminal:

```sh
cd ~/.vim/bundle
git clone https://github.com/Quramy/vim-js-pretty-template
```

## Usage

This plugin provides the `:JsPreTmpl` command.  For example:

```vim
:JsPreTmpl html
```

executing the above, a template string is highlighted with HTML way.

This command requires an argument. It's a `FileType` name which you can apply into templates in your JavaScript code.

If you want to apply automatically, you can append the following to your `.vimrc`:

```vim
autocmd FileType javascript JsPreTmpl html
```

### Alternative JavaScript user

vim-js-pretty-template is also compatible for TypeScript and CoffeeScript.

* TypeScript
* CoffeeScript

For example:

```vim
autocmd FileType typescript JsPreTmpl scss
```

then the following template string is highlighted:

```typescript
var tmpl: string = `
// highlighted in SCSS way
body.main {
  color: red;
}
`
```

or for example:

```vim
autocmd FileType coffee JsPreTmpl xml
```

then: 

```coffee
tmpl = """
<!-- highlighted in XML way -->
<svg:svg xmlns:svg="http://www.w3.org/2000/svg">
  <svg:circle cx="100" cy="100" r="50"></svg:circle>
</svg:svg>
"""
```

## License
This plugin is released under the MIT license, see `LICENSE.txt`.

