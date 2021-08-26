# Node.js Setup

Forked in Node.js `1.x` to `3.x`, but has been released since `4.x`

[https://nodejs.org/ja/download/releases/](https://nodejs.org/ja/download/releases/)

## Set `nodenv`

Recognize `.node-version` file

```bash
git clone https://github.com/nodenv/nodenv.git ~/.nodenv
git clone https://github.com/nodenv/node-build.git $(nodenv root)/plugins/node-build
cd ~/.nodenv && src/configure && make -C src
```

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PATH="$HOME/.nodenv/bin:$PATH" >> ~/.zshrc

eval "$(nodenv init -)" >> ~/.zshrc

source ~/.zshrc
```

After setting, quit the terminal session

```bash
nodenv install -l
nodenv install 10.14.2
nodenv global 10.14.2
nodenv rehash
node -v
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
