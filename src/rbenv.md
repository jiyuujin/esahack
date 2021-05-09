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
