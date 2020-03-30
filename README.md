# rfc-js-import-multiple
A proposal for JS `import` multiple modules.

We could allow importing multiple modules default exports with a wildcard or glob syntax:

```js
import components from './components/*`

// Now `components` looks like:
{
  ComponentOne, // from `./components/ComponentOne`
  ComponentTwo, // from `./components/ComponentTwo`
  ComponentThree, // from `./components/ComponentThree`,
  // etc.
}
```

This would be a terser way of achieving what you can to with a `index.js` file and [`export default from`](https://github.com/tc39/proposal-export-default-from) syntax. For the example above, this would look like:

```js
export ComponentOne from "./ComponentOne";
export ComponentTwo from "./ComponentTwo";
export ComponentThree from "./ComponentThree";
// etc.
```

Or without `export default from`:


```js
export { default as ComponentOne } from "./ComponentOne";
export { default as ComponentTwo } from "./ComponentTwo";
export { default as ComponentThree } from "./ComponentThree";
// etc.
```

