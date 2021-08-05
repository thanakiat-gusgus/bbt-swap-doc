# SDK

### SDK Package

> View repository on [Github](https://github.com/thanakiat-gusgus/pancake-swap-sdk.git)

## Setup Chain ID

MAINNET and TESTNET 

{% code title="@sdk/src/constants.ts" %}
```javascript
export enum ChainId {
  MAINNET = 25925,
  TESTNET = 25925
}
```
{% endcode %}

## Setup FACTORY\_ADDRESS and INIT\_CODE\_HASH

In order to work with the deployed smart contract, the `FACTORY_ADDRESS` and `INIT_CODE_HASH` constants within a node module called SDK should be configured accordingly.

{% code title="@sdk/src/constants.ts" %}
```javascript
export const FACTORY_ADDRESS = '<Factory Contract Address>'
export const INIT_CODE_HASH = '0x<Init Code Hash>'
```
{% endcode %}

## Setup X



{% code title="@sdk/src/entities/currency.ts" %}
```javascript
public static readonly ETHER: Currency = new Currency(18, 'KUB', 'KUB')
```
{% endcode %}

.gitignore Delete dist from this file

package.json change "repository": choose be your HTTP sdk github link

Terminal npm install/ yarn or yarn install npm prepublishOnly/ yarn prepublishOnly then you should dist floder and node\_moldues in sdk file



