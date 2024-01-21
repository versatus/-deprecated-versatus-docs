# Output Data

## Overview

A smart contract takes its inputs on stdin, as mentioned in the [Input Data] section, it performs whatever internal logic it needs to in order to serve its function, and then it writes its results to stdout. It does so in a standard form that allows the Versatus Protocol to be able to ensure consensus, and have the result persisted on the relevant chain.

These outputs come in the form of a series of operations to be performed on chain once consensus has been reached by the network. This list of instructions is serialised to JSON and written to stdout.

## Operations

The list of allowed operations are:
1. Create -- 
2. Transfer -- 
3. Update --
4. Burn --

## Schema

### Create

```json
{
    "program_namespace": "<string>",
    "program_id": "<string>",
    "program_owner": "<address>",
    "total_supply": "<uint256>",
    "initialized_supply": "<uint256>",
    "distribution": [
        [
            "address",
            "balance",
            [ "tokenFieldName", "tokenFieldValue" ]
        ]
    ]
}
```

## Transfer

```json
{
    "program_id": "<string>",
    "from": "<address>",
    "to": "<address>",
    "amount": "<uint256>",
    "token_ids": [ "<string>", ... ]
}
```
## Update

```json
{
    "items": [
        [
            [190,239,220,135,10,153,19,80,250,69,146,153,48,102,16,104,219,50,222,173],
            [222,173,220,135,10,153,19,80,250,69,146,153,48,102,16,104,219,50,190,239],
            [
                [
                    "Approvals",
                        {
                            "Approvals": {
                                "Insert": [
                                    [115,191,227,74,220,135,10,153,19,80,250,69,146,153,48,102,16,104,219,50],
                                    "0x7d"
                                ]
                            }
                        }
                ]
            ]
        ]
    ]
}
```

## Burn

```json
{
    "program_id": "<string>",
    "owner_address": "<address>",
    "amount": "<uint256>",
    "token_ids": [ "<string>", ... ]
}
```

