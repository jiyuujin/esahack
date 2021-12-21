# Rust

## Set `cargo`

.zshrc`に設定します。

```bash
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
```

## Install `cargo`

cargo プロジェクトを作成する。

```bash
cargo new hello --bin
cargo install cross
```

### Build by Web Assembly

ビルド後、denoサーバーで実行する。

```bash
rustup target add wasm32-unknown-unknown
cargo install wasm-gc

cargo build --target wasm32-unknown-unknown
deno run --allow-read ./public/main.js
```
