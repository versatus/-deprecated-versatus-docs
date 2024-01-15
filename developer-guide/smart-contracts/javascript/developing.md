# Developing a Smart Contract

To use this package to develop a smart contract with javascript, start by installing the `@versatus/versatus-javascript` package in your project:

```bash
yarn install @versatus/versatus-javascript
```

Lets initialize a new erc-20 contract to understand how to use the package.
```bash
npx vsjs init erc-20
```

This command will add a new `example-contract.js` file to the root of your project along with an inputs directory which will help test the contract against the Versatus WASM runtime.

```javascript
import { ERC20Contract } from '@versatus/versatus-javascript/lib/contracts';

const ERC_20_CONTRACT_NAME = 'Versatus ERC20'
const ERC_20_CONTRACT_SYMBOL = 'VRSTSERC'
const ERC_20_CONTRACT_DECIMALS = 18
const ERC_20_CONTRACT_TOTAL_SUPPLY = 100000000

const start = (input) => {
    const contract = new ERC20Contract(
        ERC_20_CONTRACT_NAME,
        ERC_20_CONTRACT_SYMBOL,
        ERC_20_CONTRACT_DECIMALS,
        ERC_20_CONTRACT_TOTAL_SUPPLY
    )
    return contract.start(input)
}

export default start
```

Now lets build the contract. This will create a `build.wasm` file in a `/dist` folder in the root of your project.

```bash
npx vsjs build example-contract.js
```

Now lets test the contract against the Versatus WASM runtime. This command will fetch the `versa.wasm` file required by your system to test Versatus-based smart contracts and test the contract against the provided json file in the command. You can use any of the json files provided during the `npx vsjs init erc-20` commands.  

```bash
npx vsjs test .inputs/sample-erc20-contract-name.json 
```

Here's the output you should see:

```bash
{
  "name": "Versatus ERC20",
  "success": true
}
```

