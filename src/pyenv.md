# Python

## Set `pyenv`

Please install `pyenv` using Homebrew

```bash
brew install pyenv
```

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export PYENV_ROOT=/usr/local/var/pyenv

if command -v pyenv 1>/dev/null 2>&1; then
  eval "$(pyenv init -)"
fi

source ~/.zshrc
```

After setting, quit the terminal session

```bash
pyenv install -l
pyenv install 3.9.1
pyenv global 3.9.1
pyenv rehash
python -v
```
