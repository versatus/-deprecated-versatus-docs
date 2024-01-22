# Input Data

## Overview

Smart contracts need to operate on tokens, accounts and balances and other things. Standards around fungible and non-fungible tokens, and others, often define specific pieces of data that a smart contract will use to control its execution. On other smart contract execution platforms, these can come in the form of arguments passed to specific functions, combined with the contract making specific calls to internal APIs, and in some cases even storing data within the contract itself.

For reasons of security, performance and overall reliability, Versatus Smart Contracts are stateless, and cannot make calls that access anything outside the WASM runtime.

Instead, all input _into_ a smart contract comes via stdin as a JSON object. The smart contract then parses it and can operate on the data from there. In the case of common contract types, Versatus has developer helper code and interfaces to make it easy to quickly build these common contracts, including doing the work of parsing the JSON into well-defined data structures.

## Schema

### Top-level Object

The structure of the JSON input is as follows:

```json
{
    "version": "<int>",
    "accountInfo": "<AccountInfo>",
    "function": "<string>",
    "inputs": "<JSON>"
}
```

And descriptions of the above attributes:

* `version` -- The version of the schema of this JSON input object. Currently always 1.
* `accountInfo` -- An object containing information from the blockchain about the account associated with this contract. This is prepopulated by the Versatus Network Protocol before a contract is executed. The data structure itself is documented below.
* `function` -- The contract function to enact. This will often map to specific in-language functions in the case of common contract types (for example, the string "transfer" might cause a contract to call a Rust function called `transfer()` in an ERC20 contract implementation for example). This is a convenience, however, and not a hard requirement.
* `inputs` -- The inputs to that contract as JSON (see the example below). In the case of well-known contract types, such as fungible and non-fungible tokens, Versatus has provided data structures and helper code to be able to parse and manipulate these using the constructs of your chosen language. However, this data is defined by the contract developer, along with the developer-maintained schema definition, and passed in when the contract is executed.

### AccountInfo Structure

The `AccountInfo` structure used in the `accountInfo` field above is as follows:
```json
{
    "programNamespace": "<string>",
    "linkedPrograms": { "<key>": "<LinkedProgram>"},
    "data": "<string>"
}
```

Descriptions of the above attributes:

* `programNamespace` -- A string representing the name within a namespace for this program. A program is the quivalent of a contract, but may include other types of executable job later.
* `linkedPrograms` -- References to other programs/contracts that are related to this program/contract.
* `data` -- Arbitrary opaque data owned and used by the account holder
* `key` -- The key is the same value as in the `programId` in the `LinkedProgram` structure below.

### LinkedProgram Structure
```json
{
    "programId": "<string>",
    "ownerId": "<address>",
    "balance": "<uint256>",
    "tokenIds": "[<uint256>],
    "allowances": "[ (<address>, <balance>) ]",
    "approvals": "[<address>]",
    "data": "<string>",
    "status": "<enum int>",
}
```

Descriptions of the above attributes:

* `programId` -- A string identifier within the developer's namespace to identify a program/contract that this program/contract is linked to.
* `ownerId` -- The address of the owner of the linked program/contract.
* `balance` -- The balance of the linked program.
* `tokenIds` -- A list/vector of token IDs maintained by this program/contract
* `allowances` -- A list/vector of allowances that this program/contract is authorised to spend. An allowance is a key and value representing an owner address and a balance.
* `approvals` -- A list/vector of approvals that this program/contract is authorised for. An approval is a spender address and value.
* `data` -- Arbitrary opaque data owned and used by the account holder.
* `status` -- The status of the program/contract. It is an enum of a handful of specific possible states/values.

## Sample JSON

Here is a somewhat complete example containing some sample data, as an illustration of what the JSON input might look like:

```json 
{
  "version": 1,
  "accountInfo": {
    "programNamespace": "versatus.contract.escrow",
    "linkedPrograms": {
      "versatus.contract.swap": {
        "programId": "versatus.contract.swap",
        "ownerId": "0x0123456789abcdef0123456789abcdef01234567",
        "balance": "987543856732489734298472",
        "tokenIds": [
          "0x0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef",
          "0x0123456789abcdef0123456789abcdef0123456789abcdef0123456789abcdef"
        ],
        "allowances": {
          "0x0123456789abcdef0123456789abcdef01234567": "98795837957435983"
        },
        "approvals": {
          "0x0123456789abcdef0123456789abcdef01234567": "98798754935739854"
        },
        "data": "VmVyc2F0dXMgTGFicyBGb3IgVGhlIFdpbiEK",
        "status": "0x0123"
      }
    },
    "data": "VmVyc2F0dXMgTGFicyBDaGFuZ2luZyBUaGUgR2FtZSEK"
  }, 
  "function": "revoke",
  "inputs": {
    "escrowNamespace": "namespace.of.escrow.contract.account",
    "depositId": "0xdead00000000000000000000000000000000000000000000000000000000beef",
    "depositorAddress":"0x0000000000000000000000000000000000030301",
    "timestamp": "0x65a9c7a0",
    "maturity": "0x65a9c1aa"
  }
}
```
