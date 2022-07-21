# cross-dirname

[Node.js](https://nodejs.org) + [Gjs](https://gjs.guide/) + [Deno](https://deno.land/) module that returns the current script dirname. Similar to `__dirname` but also works in CommonJs and ES modules.  

## Installation

On Node.js and GJS you can install the package as with NPM:

```
npm install cross-dirname --save
```

On Deno you just need to import this package:

```ts
import dirname from 'https://deno.land/x/cross_dirname/mod.ts';
```

## Usage

### Node.js ESM

```js
// /path/to/the/script.mjs
import dirname from 'cross-dirname'

console.log(dirname()) // outputs "/path/to/the"
```

### Node.js CJS

```js
// /path/to/the/script.cjs
console.log(require('cross-dirname')() === __dirname) // true
```

### Deno

```ts
// /path/to/the/script.ts
import dirname from 'https://deno.land/x/cross_dirname@v0.0.4/mod.ts';
console.log(dirname()); // outputs "/path/to/the"
```

### GJS

You can use NPM packages in GJS with a bundler like [esbuild](https://esbuild.github.io/).

Take a look at the examples for an [GJS + esbuild example](/examples/gjs), you can start the example like this: 

```bash
# Install dev dependencies 
npm install

# Go to the example
cd examples/gjs

# Bundle src/index.js
node esbuild.mjs

# Run the bundled index.js
gjs -m index.js
```

### Examples

You can run the examples with

```bash

npm install
npm run build

deno run ./examples/deno/index.ts 
# -> /.../examples/deno

node ./examples/node/index.cjs 
# -> /.../examples/node

node ./examples/node/index.mjs 
# -> /.../examples/node

node ./examples/gjs/esbuild.mjs
gjs -m ./examples/gjs/index.js 
# -> /.../examples/gjs
```

### Contributions

Contributions for more platforms are welcome :)

### Tests

This module has been tested on the following platforms:

| Runtime | Type   | Platform | State    |
|---------|--------|----------|----------|
| Node.js | CJS    | Linux    | ✔        |
| Node.js | CJS    | MacOS    | ✔        |
| Node.js | CJS    | Windows  | ✔        |
| Node.js | ESM    | Linux    | ✔        |
| Node.js | ESM    | MacOS    | ✔        |
| Node.js | ESM    | Windows  | ✔        |
| Deno    | ESM    | Linux    | ✔        |
| Deno    | ESM    | MacOS    | ✔        |
| Deno    | ESM    | Windows  | ✔        |
| Gjs     | ESM    | Linux    | ✔        |
| Gjs     | ESM    | MacOS    | UNTESTED |
| Gjs     | ESM    | Windows  | UNTESTED |
| Gjs     | NO-ESM | Linux    | TODO     |
| Gjs     | NO-ESM | MacOS    | TODO     |
| Gjs     | NO-ESM | Windows  | TODO     |
| Chrome  | ESM    | Browser  | NO ERROR |
| Chrome  | CJS    | Browser  | NO ERROR |

You can run all tests with:

```
npm run test
```

Or the tests for a special runtime:

```
npm run test:node
npm run test:deno
npm run test:gjs
npm run test:browser´
```