# Go

## Set `goenv`

Please install `goenv` using Homebrew

```bash
brew install goenv
```

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$PATH

source ~/.zshrc
```

Pass the path to use `goenv`

```bash
sudo vi ~/.zshrc

export GOENV_ROOT=$HOME/.goenv
export PATH=$GOENV_ROOT/bin:$PATH
export PATH=$HOME/.goenv/bin:$PATH
eval "$(goenv init -)"

source ~/.zshrc
```

After setting, quit the terminal session

List of `Go` versions that can be installed

```bash
goenv install -l
goenv install 1.11.4
goenv global 1.11.4
goenv rehash
go version
```

## Run Go simplify

[Package fmt](https://golang.org/pkg/fmt/) is an input / output package

```go
package main

import "fmt"

func main() {
    fmt.Printf("hello, world\n")
}
```
