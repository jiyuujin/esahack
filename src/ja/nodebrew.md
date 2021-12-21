# Node.js Setup

Node.js `1.x` から `3.x` でフォークされたが、 `4.x` からリリースされている。

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Set `nodebrew`

`.node-version` ファイルを認識する。

```bash
brew install nodebrew
```

`.bash_profile` に設定します。

```bash
curl -L git.io/nodebrew | perl - setup
source ~/.bash_profile
```

設定後、ターミナルセッションを終了する。

```bash
nodebrew list
nodebrew install-binary latest
nodebrew use v9.11.1
```

Node.js のバージョンを確認することができます。

### Use `npm`

`npm` のバージョンを確認することができます。

```bash
npm -v
```

### Use `yarn`

`yarn` をインストールすると、`yarn` のバージョンを確認することができます。

```bash
npm i -g yarn
yarn -v
```

#### Use `yarn link`

[https://yarnpkg.com/lang/ja/docs/cli/link/](https://yarnpkg.com/lang/ja/docs/cli/link/)

`webneko-blog` の引数に `@nekohack/j-stylebook` を指定し、`yarn link` を実行します。

```bash
yarn link @nekohack/j-stylebook
```

`webpack4` の `--progress` オプションと `--watch` オプションで確認できます。

```json
"script":  {
    "watch": "webpack --progress --config=webpack.config.js --watch",
}
```
