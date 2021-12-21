# Rollup usage

`rollup.config.js` を記述する。基本的に `.babelrc` の出力モジュールは CommonJS から ES2015 に変更する必要がある。

```js
import resolve from '@rollup/plugin-node-resolve'
import commonjs from '@rollup/plugin-commonjs'

export default {
  input: './src/index.ts',
  output: {
    file: './dist/bundle.js',
    format: 'umd',
    sourcemap: true
  },
  plugins: [
    resolve(),
    commonjs(),
  ],
}
```

### Correspond to TypeScript

TypeScript で書かれたソースに、プラグイン `@rollup/plugin-typescript` (非公式プラグイン `rollup-plugin-typescript2` のインストールに使用) をインストールします。

```js
import typescript from '@rollup/plugin-typescript'

export default {
  plugins: [
    typescript(),
  ],
}
```

### Use SCSS files

SCSS で書かれたソースのプラグイン `rollup-plugin-scss` をインストールします。

```js
import scss from 'rollup-plugin-scss'

export default {
  plugins: [
    scss(),
  ],
}
```

### Minify compiled JavaScript files

プラグイン `rollup-plugin-terser` をインストールし、JavaScript で書かれたコンパイル済みファイルを minify してください。

```js
import { terser } from 'rollup-plugin-terser'

export default {
  plugins: [
    terser(),
  ],
}
```

## Build in Preact

Preact でビルドするには externals を設定する必要があります。

```js
import sucrase from '@rollup/plugin-sucrase'

export default {
  output: {
    globals: {
      'preact': 'Preact',
      'preact-emotion': 'PreactEmotion'
    }
  },
  external: ['preact', 'preact-emotion'],
  plugins: [
    sucrase({
      exclude: ['node_modules/**'],
      transforms: ['jsx'],
      jsxPragma: 'h',
      jsxFragmentPragma: 'Fragment'
    }),
  ]
}
```

## Repositories

- [https://github.com/jiyuujin/stylebook-next](https://github.com/jiyuujin/stylebook-next)
