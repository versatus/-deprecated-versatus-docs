# Publishing Smart Contracts

Regardless of the language you develop your smart contracts in, they are compiled down to Web Assembly and then all published to the Verastus network in the same way. Publishing your smart contract to the Versatus network allows it to be executed to generate transactions for any of the blockchains supported by Versatus.

Publishing your smart contract involves wrapping it in a little metadata as a web3-native package. To make this as simple and streamlined as possible, you can use the same `versatus-wasm` CLI tool for publishing contracts as well as testing them as shown in earlier chapters.

To publish a contract, simply involve the `publish` subcommand of the `versatus-wasm` command. This subcommand takes four options:

* `-a`, `--author <AUTHOR>` -- The author of the package. May be an empty string.
* `-n`, `--name <NAME>` -- The name of the package to create. May be an empty string.
* `-v`, `--version <VERSION>` -- The version of the package.
* `-w`, `--wasm <FILE>` -- A.The path to the WASM object file to package and publish

The author, name and version are not significant when it comes to the execution of, or the security of, a smart contract. These pieces of metadata are simply there for the benefit of the developer.

When a package is published, a long _content ID_ string will be displayed. Make a note of this string, as it is how your contract is identified on the Versatus network. Rather than identifying your contract by a server it's stored on somewhere, the Versatus network uses _content addressing_. The _content ID_, or _CID_, contains a hash of content that is your web3 package and smart contract. This allows the network to store the contract wherever is best for the network, with the guarantee that you are always executing the specific contract bytes that you compiled and published.

```bash
dev@versatus:~/src/versatus-erc20$ ./versatus-wasm publish 
    --author "Versatus Labs" \
    --name "Compute Unit ERC20 Token" \
    -v 1 \
    -w target/wasm32-wasi/release/erc20.wasm 

Content ID for Web3 Package is bafyreibm74yylrtyre2tqnhhabz5vixzogjyoff4ed5xbw2vouiqn4yu6e
dev@versatus:~/src/versatus-erc20$
```
