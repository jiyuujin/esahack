# Node.js

Forked in Node.js `1.x` to `3.x`, but has been released since `4.x`

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Run JavaScript simplify

You create `src/main.js`.

```js
const main = () => {
    console.log('It is JavaScript!!');
};

main();
```

You can confirm the log `It is JavaScript!!`, it's OK!!

```bash
node src/main.js

It is JavaScript!!
```

## Run TypeScript simplify

Install `ts-node` plugin.

```bash
npm i -D ts-node typescript

yarn add ts-node typescript -D
```

You create `tsconfig.json`.

```bash
./node_modules/.bin/tsc --init
```

Additionally you create `src/main.ts`, check tyoe definition by run `./node_modules/.bin/tsc --noEmit`.

```ts
const main = () => {
    console.log('It is TypeScript!!');
};

main();
```

You can confirm the log `It is TypeScript!!`, it's OK!!

```bash
./node_modules/.bin/ts-node src/main.ts

It is TypeScript!!
```

## Manage Node.js

- [nodenv](nodenv.md)
- [nodebrew](nodebrew.md)
