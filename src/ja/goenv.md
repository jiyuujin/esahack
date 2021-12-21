# Go

## Set `goenv`

Homebrew を使って `goenv` をインストールしてください。

```bash
brew install goenv
```

`.zshrc` に設定します。

```bash
sudo vi ~/.zshrc

export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$PATH

source ~/.zshrc
```

`goenv` を使用するパスを指定します。

```bash
sudo vi ~/.zshrc

export GOENV_ROOT=$HOME/.goenv
export PATH=$GOENV_ROOT/bin:$PATH
export PATH=$HOME/.goenv/bin:$PATH
eval "$(goenv init -)"

source ~/.zshrc
```

設定後、ターミナルセッションを終了する。

インストール可能な `Go` のバージョン一覧。

```bash
goenv install -l
goenv install 1.11.4
goenv global 1.11.4
goenv rehash
go version
```

## 簡単に Go を実行する

[fmt パッケージ](https://golang.org/pkg/fmt/) は入出力パッケージです。

```go
package main

import "fmt"

func main() {
    fmt.Printf("hello, world\n")
}
```
