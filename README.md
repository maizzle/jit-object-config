## About

This repo reproduces the issue described here:

https://github.com/tailwindlabs/tailwindcss/issues/4094

## Getting Started

1. Make sure you have the Maizzle CLI installed:

```sh
# install the CLI globally
npm i -g @maizzle/cli
```

2. Clone this repo:

```sh
git clone https://github.com/maizzle/jit-object-config
```

3. `npm install` dependencies

4. Build for production:

```sh
maizzle build production
```

The build should hang.

If you edit `tailwind.config.js` and use the simplified array syntax `purge` instead of the object one, it'll work.

To check the Tailwind config object that is being used, you can edit `node_modules/@maizzle/framework/src/generators/tailwindcss.js` and add this just before the `return` statement:

```js
console.log(merge(coreConfig, tailwindConfigObject))
```
