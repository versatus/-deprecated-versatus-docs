<p align="center">
    <a href="https://discord.gg/versatus" alt="Discord">
        <img src="https://img.shields.io/discord/1034112774789414963.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2&style=for-the-badge" />
    </a>
    <a href="https://twitter.com/VersatusLabs?s=20" alt="Twitter">
        <img src="https://img.shields.io/twitter/follow/VersatusLabs?style=for-the-badge&logo=twitter&logoColor=white&labelColor=1DA1F2&color=1DA1F2" />
    </a>
</p>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/versatus/brand-assets/blob/33cf3981d13f439a43ddfde5966a8a5fd58ff5ce/logo/versatus_logo_white.png">
  <img alt="VRRB Logo" src="https://github.com/versatus/brand-assets/blob/33cf3981d13f439a43ddfde5966a8a5fd58ff5ce/logo/versatus_logo_white.png">
</picture>

### Welcome

Hey builders, welcome to the Versatus family where every line of code contributes to a larger vision – one where development is intuitive, accessible, and empowering. We know building smart contracts and decentralized applications in Web3 can seem complicated, exclusive, and exhaustive as a developer. That’s because currently, it is. But it doesn’t have to be that way, and it definitely won’t stay that way with Versatus.

### Who We Are

Versatus is the Universal Decentralized Application (dApp) Engine that allows all developers to truly build without barriers.

### Why Build on Versatus

### Flexibility
Developers can build smart contracts in familiar programming languages such as Rust, JavaScript, Go, C++, Python, C, and more. Eliminating the barriers to entry in blockchain development invites a wider pool of talent and doing so breeds familiarity efficiency and creativity, leading to more quality and diverse applications.

### Cross-Chain Settlement
In a blockchain ecosystem that is becoming increasingly fragmented, the ability to interact across different chains is invaluable. Versatus provides the necessary infrastructure for their developers to integrate contracts on their blockchain network(s) of choice.

### Scalability
 By allowing off-chain execution of smart contracts, Versatus developers benefit from reduced operational costs, improved scalability, and overall enhanced dApp performance and user experience. 

Unlike other projects, we won’t pigeonhole you into a certain or limited range of languages or a single chain. There is no Web3 prerequisite or steep learning curve. Rather than struggling with new languages and tools, our developers can focus on innovating their dApps.

### To get started building on Versatus, start [here](https://docs.versatus.io/developer-guide/smart-contracts/introduction/overview)



<br>

<hr>
<br>

<div align="center">
  <img src="https://github.com/versatus/brand-assets/blob/33cf3981d13f439a43ddfde5966a8a5fd58ff5ce/memes/fexible-text.gif" alt="nowthatsflexible.gif">
</div>
<br>
<hr>
<br>


<br>
<hr>

Scroll to the bottom for information on how to start a node.

### High Level Roadmap

This is extremely high level, for each **Epic** there are multiple features
and under each feature there are many stories and tasks

_Items that are more than 50% complete are marked with :construction: while
items that are less than 50% complete are marked as :x:, all items marked with
:white_check_mark: are complete, tested, and integrated into the node runtime_

:link: : Alphanet
:signal_strength: Betanet
:computer: Devnet

| **Epic**                  | _Description_                                                                                                                                                                                               | State              | Network           |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ | ----------------- |
| Network                   | P2P Network enabling communication between network participants                                                                                                                                             | :white_check_mark: | :link:            |
| Election                  | Proof of Claim Algorithm Implementation and Integration                                                                                                                                                     | :white_check_mark: | :link:            |
| Genesis Quorum Protocol   | Formation of the first quorums at Genesis event                                                                                                                                                             | ✅     | :link:            |
| Key Generator             | Protocol to generate Dealerless Distributed Keypairs for validator nodes, and ECDSA keypairs for all nodes                                                                                                  | :white_check_mark: | :link:            |
| State Store               | Left-Right Wrapped Accounts Database and State Trie                                                                                                                                                         | ✅                 | :link:            |
| Mempool                   | Left-Right Wrapped Pending Transaction Store                                                                                                                                                                | :white_check_mark: | :link:            |
| Validator Unit            | Left-Right enabled transaction validation protocol                                                                                                                                                          | :white_check_mark: | :link:            |
| Farmer-Harvester          | Farmer-Havester Quorum model for secure parallel execution and validation of transactions                                                                                                                   | ✅                 | :link:            |
| DAG                       | Rounds based Directed Acyclic Graph to append blocks to                                                                                                                                                     | :white_check_mark: | :link:            |
| Miner Unit                | Protocol for consolidating proposal blocks produced by miners into a single point of reference signifying the end of a round and finality of transactions (once certified)                                  | :white_check_mark: | :link:            |
| Scheduler                 | Decentralized task buffer and allocator to maximize efficiency of Farmer Quorum nodes                                                                                                                       | :white_check_mark: | :link:            |
| Block Production          | Enables harvesters to produce conflict minimized, extractable value maximized proposal blocks to be appended to the DAG                                                                                     | :white_check_mark: | :link:            |
| Node CLI                  | Provides an interface for operators to spin up a Versatus node                                                                                                                                                  | :white_check_mark: | :link:            |
| Wallet CLI                | Provides an interface for users to interact with the Versatus network                                                                                                                                           | 🚧     | :link:            |
| Token Emission Protocol   | Ensures that the proper number of tokens in each block and epoch are produced                                                                                                                                      | :white_check_mark: | :signal_strength: |
| Fee Model                 | Provides economic incentives to operators beyond emission subsidy, provides token burning to limit inflation, and economic incentives to maintain speed at scale                                            | :x:                | :signal_strength: |
| Reputation Tracking       | Tracks the reputation of nodes, and the message credits, to align incentives, reduce malicious behavior and allow for dynamic stake calculation to prevent accumulation and centralization of staking nodes | :construction:     | :signal_strength: |
| Dynamic Stake Calculator  | Protocol to calculate the minimum required stake of nodes in the network in order for the given nodes to become eligible as validators                                                                          | :x:                | :signal_strength: |
| Block Indexer             | Indexes, sequences and stores blocks for display in UIs that need access to block and transaction data                                                                                                      | :construction:     | :signal_strength: |
| Block Explorer            | Provides a web based user interface for scanning blocks, tracking transactions, etc.                                                                                                                        | :construction:     | :signal_strength: |
| Node Metrics              | Tracks the performance of a given node, cluster of nodes, and/or all nodes in the network                                                                                                                   | :x:                | :signal_strength: |
| Rent Model                | Provides economic incentives to developers to build small, modular programs that do one thing well, and link them together by returning commands to the orchestration network.                              | :x:                | :computer:        |
| Whistleblower Protocol    | Protocol for reporting malicious behavior, and initiating a stake slashing vote                                                                                                                             | :x:                | :computer:        |
| Wallet GUI                | Provides a user interface for interacting with Versatus network                                                                                                                                                 | :x:                | :computer:        |
| Unikernel Compute Runtime | Enables programming language agnostic compute in the Versatus network                                                                                                                                           | :x:                | :computer:        |

### Starting a Node

In order to start a node, run `cargo run`
Running `cargo run -- -help` will display available cli flags for node configuration and management.

**The above builds and runs a Versatus node in `debug` mode** to run in optimized
release mode you must first build the release target using the following command:

```
git clone https://github.com/versatus/versatus
cd /path/to/cloned/repo
cargo build --release
```

This will produce a target file (and directory if this is your first time
running `cargo run` or `cargo build` in this repo.

Then, to display the available CLI flags, you can run:

```
cd target/release
./versatus -help
```
