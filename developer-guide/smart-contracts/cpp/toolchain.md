# Dependencies and Toolchain

In order to build smart contracts for the Versatus network written in C++, we need to be able to compile the C++ code to Web Assembly (WASM). We have tested the [Emscripten](https://emscripten.org/) compiler, but anything that supports compiling C++ to WASM+WASI ought to suffice.

To install Emscripten, we recommend following the instructions in the [Emscripten project](https://emscripten.org/docs/getting_started/downloads.html) for your development platform of choice. Note too that Windows, MacOS and Linux have additional platform-specific suggestions and requirements. The installation of CMake and Python on Linux, for example.

Versatus has one additional dependency it needs on top of those required by Emscripten. Because our smart contract SDK needs a JSON parser, and C++ does not ship with a standard JSON parser as other languages might, we depend on the [jlohmann JSON implementation](https://github.com/nlohmann/json). You can install this with a local package manager on some Linux distributions -- for example, on Ubuntu:

```bash
sudo apt install jlohmann-json3-dev
```

It is also possible to download the single-header version of it, place it anywhere your compiler can find it, or use the `-I` option common to many C++ compilers to find it.
