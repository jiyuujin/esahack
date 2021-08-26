# Ruby

## Command Line Tools

Install Command Line Tools

```bash
xcode-select --install
xcodebuild -version
```

## Set `rbenv`

Please install `rbenv` using Homebrew

```bash
brew install rbenv ruby-build
```

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"

source ~/.zshrc
```

After setting, quit the terminal session

List of `Ruby` versions that can be installed

```bash
rbenv install --list
rbenv install 3.0.1
rbenv global 3.0.1
rbenv rehash
ruby -v
```

## Install bundler

Confirm the `bundler` version

```bash
bundler -v
```

### Install PostgreSQL

Install PostgreSQL

```bash
brew install postgresql
```

## Rails setup

I couldn't install it properly without the following steps

```bash
gem install rake
```

[New mimetic version licensed under MIT #41757](https://github.com/rails/rails/issues/41757#issuecomment-808362531)

```bash
brew install shared-mime-info
update-mime-database /usr/local/share/mime
```

Install Rails, create the skeleton of your Rails app

```bash
gem install rails -v 5.2.3
rails _5.2.3_ new . -d postgresql --skip-bundle
```

### Start at Rails

Install various `gems`

```bash
bundle install --path vendor/bundle
```

Start [http://localhost:3000](http://localhost:3000) with PostgreSQL

```bash
brew services start postgresql
rails s
```
