# Node.js

Node.js `1.x` から `3.x` でフォークされたが、 `4.x` からリリースされている。

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Run JavaScript simplify

`src/main.js`を作成します。

```js
const main = () => {
    console.log('It is JavaScript!!');
};

main();
```

ログに `It is JavaScript!!!` と表示されれば OK です。

```bash
node src/main.js

It is JavaScript!!
```

## Run TypeScript simplify

プラグイン `ts-node` をインストールします。

```bash
npm i -D ts-node typescript

yarn add ts-node typescript -D
```

`tsconfig.json` を作成します。

```bash
./node_modules/.bin/tsc --init
```

さらに、`src/main.ts` を作成したら、`./node_modules/.bin/tsc --noEmit` を実行して、tyoe の定義を確認します。

```ts
const main = () => {
    console.log('It is TypeScript!!');
};

main();
```

ログで `It is TypeScript!!!` と確認できます。

```bash
./node_modules/.bin/ts-node src/main.ts

It is TypeScript!!
```

## Manage Node.js

- [nodenv](nodenv.md)
- [nodebrew](nodebrew.md)
