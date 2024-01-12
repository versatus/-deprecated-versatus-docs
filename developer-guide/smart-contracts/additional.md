# Additional Notes

## Adding Support For Additional Languages

Currently, the requirements on a given language for being supported as a smart contract development language on Versatus is very minimal. There are only two requirements:

1. That the language can be compiled down to a Web Assembly execution target, and
2. That the Web Assembly target supports the WASI systems interface. Behind the scenes, Versatus smart contracts are passed in all of their state as JSON on `stdin` and write all of their output on `stdout`.

Other than that, we use language-specific constructs such as _Abstract Classes_, _Traits_ or _Interfaces_ to templatise common smart contract patterns for developers. This isn't strictly required, but makes it easier for developers.

