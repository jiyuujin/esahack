# PHP

## Set `phpenv`

```bash
git clone https://github.com/CHH/phpenv.git
git clone https://github.com/CHH/php-build.git ~/.phpenv/plugins/php-build
cd phpenv/bin
./phpenv-install.sh
```

`.bash_profile` に設定します。

```bash
sudo vi ~/.bash_profile

export PATH="$HOME/.phpenv/bin:$PATH"
eval "$(phpenv init -)"

source ~/.bash_profile
```

PHP を使うのは難しいので、`re2c`, `libmcrypt`, `libxml2`, `autoconf`, `automake` をインストールすることになります。

```bash
brew search bison
echo 'export PATH="/usr/local/opt/bison@2.7/bin:$PATH"'

brew install libxml2
echo 'export PATH="/usr/local/opt/libxml2/bin:$PATH"'
```

設定後、ターミナルセッションを終了する。

インストール可能な`PHP`のバージョン一覧。

```bash
phpenv install --list
phpenv install 7.2.13
phpenv global 7.2.13
phpenv rehash
php -v
```

## Install `composer`

composer プロジェクトを作成する。

```bash
git clone https://github.com/ngyuki/phpenv-composer.git ~/.phpenv/plugins/phpenv-composer
composer --version
```
