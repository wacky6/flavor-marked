Blogging Friendly Markdown
===

# Install:
npm install wacky6/bfm

# Usage:
```JavaScript
var bfm  = require('bfm')
/* tweak makred module before conversion */
bfm.marked.setOptions({ /* options */ })

var result = bfm.bfm('# bfm')
console.log(result.html)
console.log(result.meta)
```

### bfm(markdown)
##### markdown
type: `string`
Markdown string to convert
##### return
on Success: 
```JavaScript
{
    html: html,   // String, converted html
    meta: meta    // Object, metadata in bfm
}
```
on Failure:  
`null`

### bfm.marked
type: `Object`
Underlying `marked` module, you tweak it before conversion.  
`gfm` options is always set to `true`



# BFM Syntax
Basically, **BFM** = [**GFM**](https://help.github.com/articles/github-flavored-markdown/) + **YAML MetaData**
#### MetaData format:
```
[](~
    /* valid yaml document here */
~)
```
MetaData is a YAML document, that can be parsed by `js-yaml`  

if BFM is parsed by other markdown processor, `[](~ ~)` generally translates to an empty `<a>`



# Syntax Highlight
Syntax highlight is built-in, using `highlight.js`
Remember to include stylesheet in final document  
  Try one at [highlight.js](https://highlightjs.org/)
  CSS files can be found at [Github](https://github.com/isagalaev/highlight.js/tree/master/src/styles)



# Note
list of possible future features can be found in [PLANNING.md](./PLANNING.md)

MIT License, See [./LICENSE](./LICENSE) for details
