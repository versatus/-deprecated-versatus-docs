# Building a Smart Contract

Compiling your smart contract code to a WASM smart contract for Versatus is the same as building any other Rust project using the cargo build command. All that's needed is to specify the `wasm32-wasi` target when building your project. This can either be done on the command line each time (don't forget!) or may be set in your [config.toml](https://github.com/versatus/versatus-rust/blob/main/.cargo/config.toml) file. From the command line, just include the `--target` options:

```shell
cargo build --target wasm32-wasi
```

To build the ERC20 example contract, you can use the standard `cargo build --example` command:

```shell
cargo build --example erc20
```

Note that in this case, we didn't specify the target to be `wasm32-wasi` on the command line. This is because this crate's `config.toml` file sets the default target.

In both cases, your `target/` directory should contain the compiled WASM file for your project. In the case of the example above, this would likely be something like `target/examples/erc20.wasm`.
