# MultiCall

A React + Redux library for fetching, batching, and caching chain state via the MultiCall contract.

## Setup

`yarn add @intrinsic-finance/multicall` or `npm install @intrinsic-finance/multicall`

## Usage

The usage of this library is similar to [RTK Query](https://redux-toolkit.js.org/rtk-query/overview#create-an-api-slice).

```js
// Somewhere in your app
export const multicall = createMulticall({ reducerPath: 'multicall' })

// In your store's root reducer
export const rootReducer = combineReducers({
  // Other reducers
  [multicall.reducerPath]: multicall.reducer
})
```

To use the updater, you'll need an instance of the Intrinsic Multicall2 contract:

```js
import { abi as MulticallABI } from '@intrinsic-finance/periphery/artifacts/contracts/lens/IntrinsicInterfaceMulticall.sol/IntrinsicInterfaceMulticall.json'
import { Contract } from 'ethers'
import { IntrinsicInterfaceMulticall } from './abi/types'

const multicall2Contract = new Contract(address, MulticallABI, provider) as IntrinsicInterfaceMulticall
```

## Alpha software

The latest version of the SDK is used in production in the Intrinsic Interface,
but it is considered Alpha software and may contain bugs or change significantly between patch versions.
If you have questions about how to use the SDK, please reach out in the `#dev-chat` channel of the Discord.
Pull requests welcome!
