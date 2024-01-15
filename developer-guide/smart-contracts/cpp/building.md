# Building a Smart Contract

In order to build your smart contract, ensure that you have the Emscripten compiler installed and working, and that you have the JSON parser mentioned in the previous step on dependencies, and simply compile your code. Assuming that the JSON parser is in the search path for the compiler, the following ought to suffice:

```bash
em++ -std=c++20 -o contract.wasm contract.cpp
```
