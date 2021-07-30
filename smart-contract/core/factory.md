# Factory

## Overview

Factory defines the generic logic for generating pools. Where a pool is referred to two tokens, which make up the asset pair, and a fee. Its primary job is to create one and only one smart contract per unique token pair. It also contains logic to turn on the protocol charge.

### Code

> [PancakeFactory.sol](https://github.com/BBT-DeFi/BBT-Swap/blob/main/core/contracts/PancakeFactory.sol)

### Address

`0x384e8898B437953257265E65F32201cDF100ae5C`

## Setup Your Address

{% code title="@sdk/src/constants.ts" %}
```text
export const FACTORY_ADDRESS = '<Factory Contract Address>
export const INIT_CODE_HASH = '<Init code hash>'
```
{% endcode %}
