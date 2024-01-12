# Building a Smart Contract

Simply use the TinyGo compiler command instead of the standard Go compiler command, and specify the target as WASI:

```
tinygo build --target=wasi \
    -scheduler=none -gc=conservative \
    -o contract.wasm ./...
```

This should result in a `contract.wasm` file that is the Web Assembly smart contract.
