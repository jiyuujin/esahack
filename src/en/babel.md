# Babel usage

1. `@babel/core`
   - Core of babel, even if there is only this, nothing will do.
2. `@babel/cli`
   - Necessary to use `babel` command.
3. `@babel/preset-env`
   - Convert to a good feeling according to specified environment.

## Caution!!

### `yearly` / `stage-x` presets

Since Babel7, `yearly` / `stage-x` presets is deprecated.

- `babel-preset-es2015`
- `babel-preset-es2016`
- `babel-preset-es2017`
- `babel-preset-latest`
- `babel-preset-stage-0`
- `babel-preset-stage-1`

### `@babel/polyfill`

Since Babel7.4, `@babel/polyfill` is deprecated.

Please use `useBuiltIns` in `@babel/preset-env`, you must load polyfills of core-js@v3
