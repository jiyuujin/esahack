# Node.js Setup

Forked in Node.js `1.x` to `3.x`, but has been released since `4.x`

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Set `nodebrew`

Recognize `.node-version` file

```bash
brew install nodebrew
```

Set the config at `.bash_profile`

```bash
curl -L git.io/nodebrew | perl - setup
source ~/.bash_profile
```

After setting, quit the terminal session

```bash
nodebrew list
nodebrew install-binary latest
nodebrew use v9.11.1
```

You can confirm the versions of node.js

### Use `npm`

You can confirm the version of `npm`

```bash
npm -v
```

### Use `yarn`

Install `yarn`, you can confirm the version of `yarn`

```bash
npm i -g yarn
yarn -v
```

#### Use `yarn link`

[https://yarnpkg.com/lang/ja/docs/cli/link/](https://yarnpkg.com/lang/ja/docs/cli/link/)

Run `yarn link` in `@nekohack/j-stylebook`, set `@nekohack/j-stylebook` to the argument in `webneko-blog`.

```bash
yarn link @nekohack/j-stylebook
```

You can confirm by using `--progress` option and `--watch` option in `webpack4`.

```json
"script":  {
    "watch": "webpack --progress --config=webpack.config.js --watch",
}
```
