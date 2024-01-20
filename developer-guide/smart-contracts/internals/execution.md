# Smart Contract Execution

The WASM smart contract runtime will load and execute a single WASM binary as a smart contract. It does not handle separate modules, dynamic linking or dependencies in anyway today, but may in the future as the need arises and certain standards are ratified and become widely supported by compilers.

The entry point into every smart contract is the `_start` symbol. It is called with no arguments and returns an integer return code. This makes it very similar to the following `main()` function definition in C:

```c
int main() {

    return 0; // success
}
```

In fact, most WASM compiler and toolchains (Rust, Emscripten, LLVM, TinyGo, etc) will default to mapping that language's usual entry point (`main()` for example) to the `_start` symbol. The following Rust code compiled to the `wasm32-wasi` target will result in a `.wasm` file that can be executed under the Versatus network, albeit not doing anything.

```rust 
fn main() {
    eprintln!("Hello from Rust + WASM");
}
```

And built with something along these lines:

```shell
rustc --target wasm32-wasi ./main.rs
```

