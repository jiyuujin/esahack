# Python

## Set `pyenv`

Homebrew を使って `pyenv` をインストールしてください。

```bash
brew install pyenv
```

`.zshrc` に設定します。

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PYENV_ROOT=/usr/local/var/pyenv

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi

source ~/.zshrc
```

設定後、ターミナルセッションを終了する。

インストール可能な `Python` のバージョン一覧。

```bash
pyenv install -l
pyenv install 3.9.1
pyenv global 3.9.1
pyenv rehash
python -v
```
