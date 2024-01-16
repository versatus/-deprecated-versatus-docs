# Building a Smart Conract
C smart contracts for Versatus are compiled to WebAssembly (WASM) using Clang or GCC, along with Emscripten.

# Configure Emscripten:
Set up Emscripten on your system by following the `[Emscripten Installation Guide](https://emscripten.org/docs/getting_started/index.html).`

Compile Your Contract
Compile your C code to WASM using Emscripten. In your project directory, run:

`emcc -std=c99 -I/usr/local/include -o contract.wasm main.c -L/usr/local/lib -ljson-c`

Replace`main.c` with the path to your C source file. The output `contract.wasm` is your compiled smart contract.
