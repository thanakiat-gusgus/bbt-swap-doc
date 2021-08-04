# Factory

## Overview

Factory defines the generic logic for generating pools. Where a pool is referred to two tokens, which make up the asset pair, and a fee. Its primary job is to create one and only one smart contract per unique token pair. It also contains logic to turn on the protocol charge.

### Code

> View [PancakeFactory.sol](https://github.com/BBT-DeFi/BBT-Swap/blob/main/core/contracts/PancakeFactory.sol) on Github

### Address

Our `PancakeFactory` is deployed at `0x384e8898B437953257265E65F32201cDF100ae5C`

## Setup Your Address

In order to work with the deployed smart contract, the `FACTORY_ADDRESS` and `INIT_CODE_HASH` constants within a node module called SDK should be configured accordingly.

{% code title="@sdk/src/constants.ts" %}
```javascript
export const FACTORY_ADDRESS = '<Factory Contract Address>'
export const INIT_CODE_HASH = '0x<Init Code Hash>'
```
{% endcode %}

## Functions

### Read-Only Function

#### • getPair

```javascript
function getPair(address tokenA, address tokenB) external view returns (address pair);
```

Address for `tokenA` and address for `tokenB` return address of pair contract \(where one exists\). `tokenA` and `tokenB` order is interchangeable. Returns `0x0000000000000000000000000000000000000000` as address where no pair exists.

#### • allPairs

```javascript
function allPairs(uint) external view returns (address pair);
```

Returns the address of the `n`th pair \(`0`-indexed\) created through the Factory contract. Returns `0x0000000000000000000000000000000000000000` where pair has not yet been created. Begins at `0` for first created pair.

#### • allPairsLength

```javascript
function allPairsLength() external view returns (uint);
```

Displays the current number of pairs created through the Factory contract as an integer.

#### • feeTo

```javascript
function feeTo() external view returns (address);
```

The address to where non-LP-holder fees are sent.

#### • feeToSetter

```javascript
function feeToSetter() external view returns (address);
```

The address with permission to set the feeTo address.

### State-Changing Functions

#### • createPair

```javascript
function createPair(address tokenA, address tokenB) external returns (address pair);
```

Creates a pair for `tokenA` and `tokenB` where a pair doesn't already exist. `tokenA` and `tokenB` order is interchangeable. Emits `PairCreated` \(see Events\).

#### • setFeeTo

Sets address for `feeTo`.

#### • setFeeToSetter

Sets address for permission to adjust `feeTo`.

### Events

#### • PairCreated

```javascript
event PairCreated(address indexed token0, address indexed token1, address pair, uint);
```

Emitted whenever a `createPair` creates a new pair. `token0` will appear before `token1` in sort order. The final `uint` log value will be `1` for the first pair created, `2` for the second, etc.

