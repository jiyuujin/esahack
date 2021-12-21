# Babel usage

1. `@babel/core`
   - Babel のコア、これだけでも何もしません。
2. `@babel/cli`
   - `babel` コマンドを使用する必要があります。
3. `@babel/preset-env`
   - 指定された環境に応じて良い感じに変換します。

## Caution!!

### `yearly` / `stage-x` presets

Babel7 以降、 `yearly` / `stage-x` プリセットは非推奨になりました。

- `babel-preset-es2015`
- `babel-preset-es2016`
- `babel-preset-es2017`
- `babel-preset-latest`
- `babel-preset-stage-0`
- `babel-preset-stage-1`

### `@babel/polyfill`

Babel7.4以降、 `@babel/polyfill` は非推奨になりました。

`@babel/preset-env` で `useBuiltIns` を使用してください。core-js@v3 のポリフィルをロードする必要があります。
