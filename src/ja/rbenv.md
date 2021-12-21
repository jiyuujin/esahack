# Ruby

## Command Line Tools

コマンドラインツールのインストール。

```bash
xcode-select --install
xcodebuild -version
```

## Set `rbenv`

Homebrew を使って `rbenv` をインストールしてください。

```bash
brew install rbenv ruby-build
```

`.zshrc` に設定します。

```bash
sudo vi ~/.zshrc

export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"

source ~/.zshrc
```

設定後、ターミナルセッションを終了する。

インストール可能な `Ruby` のバージョン一覧。

```bash
rbenv install --list
rbenv install 3.0.1
rbenv global 3.0.1
rbenv rehash
ruby -v
```

## Install bundler

`bundler` のバージョンを確認する。

```bash
bundler -v
```

### Install PostgreSQL

PostgreSQL のインストール。

```bash
brew install postgresql
```

## Rails setup

以下の手順を踏まないと、うまくインストールできませんでした。

```bash
gem install rake
```

[New mimetic version licensed under MIT #41757](https://github.com/rails/rails/issues/41757#issuecomment-808362531)

```bash
brew install shared-mime-info
update-mime-database /usr/local/share/mime
```

Rails をインストールし、Rails アプリのスケルトンを作成します。

```bash
gem install rails -v 5.2.3
rails _5.2.3_ new . -d postgresql --skip-bundle
```

### Start at Rails

様々な `gems` をインストールする

```bash
bundle install --path vendor/bundle
```

PostgreSQL で [http://localhost:3000](http://localhost:3000) を起動します。

```bash
brew services start postgresql
rails s
```
