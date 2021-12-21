# Node.js Setup

Node.js `1.x` から `3.x` でフォークされたが、 `4.x` からリリースされている。

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Set `nodenv`

`.node-version` ファイルを認識する。

```bash
git clone https://github.com/nodenv/nodenv.git ~/.nodenv
git clone https://github.com/nodenv/node-build.git $(nodenv root)/plugins/node-build
cd ~/.nodenv && src/configure && make -C src
```

`.zshrc` に設定します。

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PATH="$HOME/.nodenv/bin:$PATH" >> ~/.zshrc

eval "$(nodenv init -)" >> ~/.zshrc

source ~/.zshrc
```

設定後、ターミナルセッションを終了する。

```bash
nodenv install -l
nodenv install 10.14.2
nodenv global 10.14.2
nodenv rehash
node -v
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
