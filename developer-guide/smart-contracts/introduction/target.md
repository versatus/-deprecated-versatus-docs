# Compilation and Execution Target

In order to best-support smart contract development in a broad range of languages, Versatus smart contracts are compiled from source code into a binary execution format called [Web Assembly (WASM)](https://webassembly.org/). Web Assembly is a mature and standard technology that allows for secure and performant execution of code on a variety of hardware and software plaforms, regardless of the language used to develop the software.

You can find a brief article that describes why Versatus chose Web Assembly [here](https://incomplete.io/wasm/why-wasm-versatus/index.html).

Essentially what this means is that if your favourite programming language can be compiled down to Web Assembly, there is a very good chance that it can be used to write smart contracts on Versatus. If your language of choice isn't supported by Versatus today, we'll include some notes below that enumerate the requirements for adding a new language in case you want to add your own.
