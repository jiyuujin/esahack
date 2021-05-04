# Go

## Installation

Use HomeBrew

```bash
brew install go
```

Set the config at `.zshrc`

```bash
sudo vi ~/.zshrc

# ~/.zshrc
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOROOT/bin:$GOPATH/bin:$PATH

source ~/.zshrc
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
