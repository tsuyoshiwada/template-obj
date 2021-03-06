template-obj
============

[![Build Status](http://img.shields.io/travis/tsuyoshiwada/template-obj.svg?style=flat-square)](https://travis-ci.org/tsuyoshiwada/template-obj)
[![npm version](https://img.shields.io/npm/v/template-obj.svg?style=flat-square)](http://badge.fury.io/js/template-obj)
[![Bower](https://img.shields.io/bower/v/template-obj.svg?style=flat-square)](http://bower.io/search/?q=template-obj)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://raw.githubusercontent.com/tsuyoshiwada/template-obj/master/LICENSE)

template strings in the javascript object.  
lightweight utility module. (production file is 1.29KB)



## Install

### npm

```
$ npm install template-obj
```

### Bower

```
$ bower install template-obj
```

### CommonJS

```
var templateObj = require("template-obj");
```

### Basic

1. Download the [template-obj.min.js](https://raw.githubusercontent.com/tsuyoshiwada/template-obj/master/template-obj.min.js).  
2. Load it in the script tag.

```html
<script type="text/javascript" src="template-obj.min.js"></script>
```



## Usage

### Basic

```javascript
var obj = templateObj({
  key1: "value1",
  key2: "${key1} value2"
});

console.log(obj);
/*
{
  key1: "value1",
  key2: "value1 value2"
}
*/
```


### Nested value

Access to the nested value using the dot syntax, and bracket notation.

```javascript
var params = templateObj({
  ns: "app",
  events: {
    click     : "click.${ns}",
    mouseenter: "mouseenter.${ns}",
    mouseleave: "mouseleave.${ns}"
  },
  logs: {
    click     : "${events.click} was triggered.",
    mouseenter: "${events.mouseenter} was triggered.",
    mouseleave: "${events.mouseleave} was triggered."
  },
  defaultEvent: "${events.click}",
  loaders: [
    "coffee-loader",
    "babel-loader"
  ],
  loader: "${loaders[0]} & ${loaders[1]}"
});

console.log(params);
/*
{
  ns: "app",
  events: {
    click     : "click.app",
    mouseenter: "mouseenter.app",
    mouseleave: "mouseleave.app"
  },
  logs: {
    click     : "click.app was triggered.",
    mouseenter: "mouseenter.app was triggered.",
    mouseleave: "mouseleave.app was triggered."
  },
  defaultEvent: "click.app",
  loaders: [
    "coffee-loader",
    "babel-loader"
  ],
  loader: "coffee-loader & babel-loader"
}
*/
```



## Browser Support

* IE6 +
* Chrome
* Firefox
* Safari
* iOS
* Android


## License
Released under the [MIT Licence](https://raw.githubusercontent.com/tsuyoshiwada/template-obj/master/LICENSE)


## Author
[tsuyoshi wada](https://github.com/tsuyoshiwada/)
