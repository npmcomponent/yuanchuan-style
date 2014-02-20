*This repository is a mirror of the [component](http://component.io) module [yuanchuan/style](http://github.com/yuanchuan/style). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/yuanchuan-style`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Style
Create stylesheets dynamically in JavaScript. Ported from [excss](https://github.com/yuanchuan/excss).

### Installation

```bash
component install yuanchuan/style
```


### Usage

```Javascript
var Style = require('style');
var style = new Style();

style.load(
  'body { background:blue; }',
  'p    { color: red; }'
)
```

Defining variables:

```Javascript
var style = new Style()

style.define({
  color1: '#23efab',
  color2: '#ff3233' 
})

style.load(
  'img { border: 1px @color1 solid }',
  'a:hover { border: 1px @color2 dashed }'
)
```

### More examples

Using add() to append new styles and refresh later using load():

```Javascript
style
  .define({
    color1: '#23efab',
    color2: '#ff3233'
  })
  .add(
    'img { border: 1px @color1 solid }'
  )
  .add(
    'a: hover{ border: 1px @color2 dashed }'
  )
  .load()
```

Re-defining a variable then apply:

```Javascript
style
  .define({
    color1: 'blue',
    color2: 'red'
  })
  .load() 
```

Clear all the added styles:

```Javascript
style.clear()
```

Remove completely:

```Javascript
style.remove()
```

### License

The MIT license.
