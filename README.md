[![Npm Package](https://img.shields.io/npm/v/redemo.svg?style=flat-square)](https://www.npmjs.com/package/redemo)
[![Npm Downloads](http://img.shields.io/npm/dm/redemo.svg?style=flat-square)](https://www.npmjs.com/package/redemo)
[![Dependency Status](https://david-dm.org/gwuhaolin/redemo.svg?style=flat-square)](https://npmjs.org/package/redemo)

# redemo
When you write a react component, you may need tell others how to use it by write some demos.
Redemo is used to help write demo for react component in a easy way, is't pretty and simple to use.

## install
use it in CMD
```bash
npm i redemo
```
load it in browser direct
```html
<html>
<head>
<link rel="stylesheet" href="./node_modules/redemo/dist/redemo.css">
</head>
<body>
  <script src="./node_modules/redemo/dist/redemo.js"></script>
</body>
</html>
```

## feature
- doc: write doc in markdown for this demo
- code: show source code for this demo
- propTypes: auto list react component `propTypes` document form comment in your component source instead of write by yourself

## example
Let's write a demo for a `Button` component write by you

```js
import ReDemo from 'redemo';
import Button from './button';

// load propTypes by docgen-loader from button component source code
const docgen = require('!!docgen-loader!../button');
const propTypes = docgen[0]['props'];

// load source code by raw-loader from button component source code
const code = require('!!raw-loader!../button');

// write doc for this demo in markdown
const doc = `
### react component used to demonstrate react component
#### structure
- in top section is demo instance to play 
- circle button in right are toggle for **component propTypes** and **demo source code**
- propTypes table show all prop's info for this component
- in bottom is source code for this demo
`

<ReDemo
  className="my-demo"
  title="react demo component"
  propTypes={propTypes}
  doc={doc}
  code={code}
  defaultCodeVisible
  defaultPropTypeVisible
>
  <Button>demo component instance</Button>
</ReDemo>
```

## API
see `ReDemo`'s all props [here](https://gwuhaolin.github.io/redemo/)