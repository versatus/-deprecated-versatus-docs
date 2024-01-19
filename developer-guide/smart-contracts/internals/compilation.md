# Compilation Target

Smart contracts on Versatus are compiled from any supported language down to Web Assembly (WASM) rather than being compiled for specific CPUs or for a blockchain-specific VM such as EVM. Versatus doesn't customise the WASM instruction set or runtime at all, leaving it compatible with the generally-available tools out in the community. Versatus does rely on the propsed WASI standard, as supported by most compilers under the namespace `wasi_snapshot_preview1`. Versatus will likely support the WASI module standard defined in the `wasi_snapshot_preview2` namespace once it has been standardised and is supported by more tools.

This is represented today by the Rust `wasm32-wasi` target, as a point of reference.

