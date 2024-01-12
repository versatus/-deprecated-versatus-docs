# Dependencies and Toolchain

In order to develop smart contracts for the Versatus network in the Go language, it needs to be compiled to Web Assembly (WASM) with WASI support. This is most easily done with the TinyGo embedded Go compiler.

In order to run this example on the Versatus network, it needs to be compiled to Web Assembly with WASI support. This is most-easily done using the TinyGo embedded Go compiler, but other options may work as long as there is a `_start` symbol and the module is statically linked.

With an existing Go installation, the TinyGo compiler can be installed in a variety of ways, depending on your operating system and package manager. Here are a few examples:

* `sudo apt install tinygo` -- this will work on many Debian and Ubuntu distributions.
* `sudo pacman -S tinygo` -- this will work for ArchLinux users, BTW.
* `brew tap tinygo-org/tools && brew install tinygo` -- this will work for MacOS.


Otherwise, it ought to be possible to install following instructions on the [TinyGo Releases Page](https://github.com/tinygo-org/tinygo/releases).
