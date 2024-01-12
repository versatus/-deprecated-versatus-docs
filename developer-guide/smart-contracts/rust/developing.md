# Developing a Smart Contract

To use this crate to develop a smart contract, simply import this crate as you would any other crate (eg `cargo add versatus-rust`), and define your contract from there.

The [ERC20](examples/erc20.rs) example shows an example of how to build your own ERC20 token on the Versatus network using the provided `Erc20` and `SmartContract` traits. All we need is a Rust `main()` function to define the new token type, and to call a helper function to process the inputs/outputs and to call the requested function:

```rust
use versatus-rust::*;

fn main() {
    let mut token = ComputeUnitToken { inputs: None };
    process_erc20(&mut token).unwrap();
}
```

With our `ComputeUnitToken` instantiated and passed to `process_erc20()` in our `main()` function, simply fill in the required functions/methods dictated by the `Erc20` and `SmartContract` traits and build.
 
See the [ERC20](examples/erc20.rs) example, the [crate](https://crates.io/crates/versatus-rust/) and the [crate docs](https://docs.rs/versatus-rust/latest/versatus_rust/) for additional details.
