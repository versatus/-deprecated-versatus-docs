### Dependencies and Toolchain
Keep dependencies to a minimum. Versatus smart contracts are compiled to WASM, not machine to ensure cross-platform compatibility.

### C Standard Library for WASM
You may need a standard library adapted for WebAssembly. Explore options like 
`[WASI-libc](https://github.com/WebAssembly/wasi-libc)`

### json-c Library
For contracts requiring JSON processing, use the json-c library. Clone and build it for WASM:
`git clone https://github.com/json-c/json-c
cd ~/json-c-build-wasm
emconfigure ~/json-c/cmake-configure
cd ~/json-c
emmake make
emmake make install`

After building, copy `libjson-c.a`` to your system library path.

### Add WASM Target
Emscripten supports the WASM target by default. Make sure Emscripten’s environment variables are correctly set up in your shell:
`source /path/to/emsdk/emsdk_env.sh`