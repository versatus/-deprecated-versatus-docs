# Dependencies and Toolchain

We want to keep the dependencies required down to a minimum too. Smart contracts on Versatus are compiled not to machine instructions like a regular program, but to Web Assembly instructions to allow it to be executed across any platform on the Versatus network, including standalone on your development machine, using our smart contract runtime. The Rust community provides the necessary compiler backend to compile your Rust code to WASM that is compatible with the Versatus smart contract runtime.

To add this WASM target to rust, you can use the standard `rustup` tool to add the `wasm32-wasi` target:

```shell
rustup target add wasm32-wasi
```
