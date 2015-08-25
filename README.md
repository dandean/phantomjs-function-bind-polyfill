# Spec-compliant `Function.prototype.bind` polyfill for for PhantomJS

The Mozilla `Function.prototype.bind` polyfill results in a failure during
Babel's `_classCallCheck` with this message:

> "Cannot call a class as a function"

Specifically, this would be triggered by Babel compiled code such as:

```js
var store = new (_bind.apply(_Store, [null].concat(constructorArgs)))();
```
