# Rust

## Set `cargo`

Set the config at `.zshrc`

```bash
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
```

## Install `cargo`

Create a cargo project

```bash
cargo new hello --bin
cargo install cross
```

### Build by Web Assembly

Run on deno server after build

```bash
rustup target add wasm32-unknown-unknown
cargo install wasm-gc

cargo build --target wasm32-unknown-unknown
deno run --allow-read ./public/main.js
```
