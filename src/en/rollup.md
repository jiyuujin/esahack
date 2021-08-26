# Rollup usage

Write `rollup.config.js`. Basically, output module of `.babelrc` must be changed from CommonJS to ES2015.

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

Install the plugin, `@rollup/plugin-typescript` (used to install the unofficial plugin, `rollup-plugin-typescript2`) in source written by TypeScript.

```js
import typescript from '@rollup/plugin-typescript'

export default {
  plugins: [
    typescript(),
  ],
}
```

### Use SCSS files

Install the plugin `rollup-plugin-scss` in source written by SCSS.

```js
import scss from 'rollup-plugin-scss'

export default {
  plugins: [
    scss(),
  ],
}
```

### Minify compiled JavaScript files

Install the plugin `rollup-plugin-terser`, minify compiled files written by JavaScript.

```js
import { terser } from 'rollup-plugin-terser'

export default {
  plugins: [
    terser(),
  ],
}
```

## Build in Preact

You need to set externals to build in Preact.

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
