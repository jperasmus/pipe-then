# pipe-then
A better implementation of the "pipe" FP function that allows for piping both synchronous and asynchronous functions.

## Installation:
```
yarn add pipe-then
```
or
```
npm install --save pipe-then
```

## Example:

```js
import pipe from 'pipe-then';

const double = x => x * 2;
const square = x => x * x;
const plus3 = x => new Promise(resolve => setTimeout(() => resolve(x + 3), 100));

pipe(plus3, square, double)(2)
  .then(result => // Result equals 50)
  .catch(console.error);

```