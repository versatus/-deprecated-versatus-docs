# Dependencies and Toolchain
In the JavaScript ecosystem, you can compile your JavaScript code to Web Assembly format that is compatible with the Versatus smart contract runtime. This allows you to write smart contracts using JavaScript and execute them seamlessly within the Versatus environment. The JavaScript tooling and resources that support JavaScript-based WebAssembly compilation include the following:

### Required Dependencies 
#### Node 
Node.js is a JavaScript runtime and fundamental dependency for most JavaScript-based projects, including smart contract development. It that allows you to execute  JavaScript code on your local machine and interact with various libraries and tools.

#### Yarn
Yarn is another package manager for JavaScript. It provides an efficient and reliable way to manage project dependencies, install packages, and handle versioning.. It is an alternative to npm (Node Package Manager) and offers advantages such as faster package installation. You can install Yarn by following the instructions provided on the official Yarn website: Yarn Official Website (https://yarnpkg.com/).

#### Javy
Javy is a JavaScript to WebAssembly toolchain that can create small WASM modules. The toolchain aims to be a versatile tool for anyone who wants to work with JavaScript in WASM, and it can compile QuickJS, a small JavaScript engine, to WASM along with the script to be executed. To install Javy, perform the following steps:
1. Download the latest version of the Javy package for your platform from the Bytecode Alliance Github page (https://github.com/bytecodealliance/javy/releases/)
2. Decompress the downloaded file using gunzip or another tool capable of decompressing gzip-format files (eg, ```gunzip javy-x86_64-macos-v1.2.0.gz```)
3. Make the Javy binary executable (ie, ```chmod a+x javy-x86_64-macos-v1.2.0```)
4. Optionally place the Javy binary somewhere in your PATH (eg,``` /usr/local/bin or ~/bin```) and rename it to simply javy (ie, ```mv javy-x86_64-macos-v1.2.0 /usr/local/bin/javy```) to do both in one command.
5. Test that it can be executed by running it, including the path to the executable if needed (ie ```./javy or /usr/local/bin/javy``` or simply ```javy```). Executing it without any arguments should show the usage output. Or javy --version should show the version number, also indicating it works.
