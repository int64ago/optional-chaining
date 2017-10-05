# optional-chaining

[![NPM version][npm-image]][npm-url]
[![npm download][download-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/optional-chaining.svg?style=flat-square
[npm-url]: https://npmjs.org/package/optional-chaining
[download-image]: https://img.shields.io/npm/dm/optional-chaining.svg?style=flat-square
[download-url]: https://npmjs.org/package/optional-chaining

Partial implementation for [Optional Chaining](https://github.com/tc39/proposal-optional-chaining) in ES5

## API

```js
var chain: (sourceObject: object, propertyString: string, defaultValue: any) => any
```

## Examples

`npm i optional-chaining -S`

```js
var chain = require('optional-chaining');

var testObj = {
  code: 200,
  data: {
    list: [
      { id: 1, name: 'name1' },
      { id: 2, name: 'name2' }
    ],
    page: {
      current: 1,
      total: 200
    }
  }
};

console.log(chain(testObj, '.code')); // 200
console.log(chain(testObj, '.data.page.current')); // 1
console.log(chain(testObj, '.data.list[0].id')); // 1
console.log(chain(testObj, '.wrong.path')); // undefined
console.log(chain(testObj, '.wrong.path', 666)); // 666
```

## License

MIT