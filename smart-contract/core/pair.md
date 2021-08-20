# Pair

### Code

View [PancakePair.sol](https://github.com/BBT-DeFi/BBT-Swap/blob/main/core/contracts/PancakePair.sol) on github

### Address

Our `PancakePair` is deployed at `0x2D105fF34641dc54cf7D17df7161C6867DA3f68B`

### Mint

```javascript
event Mint(address indexed sender, uint amount0, uint amount1);
```

 Emitted each time liquidity tokens are created via ~~**mint**~~.

### Burn

```javascript
event Burn(address indexed sender, uint amount0, uint amount1, address indexed to);
```

 Emitted each time liquidity tokens are destroyed via ~~**burn**~~.

### Swap

```javascript
event Swap(
        address indexed sender,
        uint amount0In,
        uint amount1In,
        uint amount0Out,
        uint amount1Out,
        address indexed to
    );
```

 Emitted each time a swap occurs via ~~**swap**~~.

### Sync

```text
event Sync(uint112 reserve0, uint112 reserve1);
```

 Emitted each time reserves are updated via ~~**mint**~~, ~~**burn**~~, ~~**swap**~~, or ~~**sync**~~.

## Read-Only Functions

### MINIMUM\_LIQUIDITY

```javascript
function MINIMUM_LIQUIDITY() external pure returns (uint);
```

 Returns `1000` for all pairs. See ~~**Minimum Liquidity**~~.

### factory

```javascript
function factory() external view returns (address);
```

 Returns the ~~**factory address**~~.

### token0

```javascript
function token0() external view returns (address);
```

Returns the address of the pair token with the lower sort order.

### token1

```javascript
function token1() external view returns (address);
```

Returns the address of the pair token with the higher sort order.

### getReserves

```javascript
function getReserves() external view returns (uint112 reserve0, uint112 reserve1, uint32 blockTimestampLast);
```

 Returns the reserves of token0 and token1 used to price trades and distribute liquidity. See ~~**Pricing**~~. Also returns the `block.timestamp` \(mod ~~_**2\*\*32**_~~\) of the last block during which an interaction occured for the pair.

### price0CumulativeLast

```javascript
function price0CumulativeLast() external view returns (uint);
```

 See ~~**Oracles**~~.

### price1CumulativeLast

```javascript
function price1CumulativeLast() external view returns (uint);
```

 See ~~**Oracles**~~.

### kLast

```javascript
function kLast() external view returns (uint);
```

 Returns the product of the reserves as of the most recent liquidity event. See ~~**Protocol Charge Calculation**~~.

## State-Changing Functions

### mint

```javascript
function mint(address to) external returns (uint liquidity);
```

Create pool tokens.

* Emits ~~**Mint**~~, ~~**Sync**~~, ~~**Transfer**~~.

### burn

```javascript
function burn(address to) external returns (uint amount0, uint amount1);
```

Destroy pool tokens.

* Emits ~~**Burn**~~, ~~**Sync**~~, ~~**Transfer**~~.

### swap

```javascript
 function swap(uint amount0Out, uint amount1Out, address to, bytes calldata data) external;
```

 Swaps tokens. For regular swaps, `data.length` must be `0`. Also see ~~**Flash Swaps**~~.

* Emits ~~**Swap**~~, ~~**Sync**~~.

### skim

```javascript
function skim(address to) external;
```

### sync

```javascript
function sync() external;
```

* Emits ~~**Sync**~~.

### Interface

```javascript
import './interfaces/IPancakePair.sol';
```

```javascript
pragma solidity >=0.5.0;

interface IPancakePair {
    event Approval(address indexed owner, address indexed spender, uint value);
    event Transfer(address indexed from, address indexed to, uint value);

    function name() external pure returns (string memory);
    function symbol() external pure returns (string memory);
    function decimals() external pure returns (uint8);
    function totalSupply() external view returns (uint);
    function balanceOf(address owner) external view returns (uint);
    function allowance(address owner, address spender) external view returns (uint);

    function approve(address spender, uint value) external returns (bool);
    function transfer(address to, uint value) external returns (bool);
    function transferFrom(address from, address to, uint value) external returns (bool);

    function DOMAIN_SEPARATOR() external view returns (bytes32);
    function PERMIT_TYPEHASH() external pure returns (bytes32);
    function nonces(address owner) external view returns (uint);

    function permit(address owner, address spender, uint value, uint deadline, uint8 v, bytes32 r, bytes32 s) external;

    event Mint(address indexed sender, uint amount0, uint amount1);
    event Burn(address indexed sender, uint amount0, uint amount1, address indexed to);
    event Swap(
        address indexed sender,
        uint amount0In,
        uint amount1In,
        uint amount0Out,
        uint amount1Out,
        address indexed to
    );
    event Sync(uint112 reserve0, uint112 reserve1);

    function MINIMUM_LIQUIDITY() external pure returns (uint);
    function factory() external view returns (address);
    function token0() external view returns (address);
    function token1() external view returns (address);
    function getReserves() external view returns (uint112 reserve0, uint112 reserve1, uint32 blockTimestampLast);
    function price0CumulativeLast() external view returns (uint);
    function price1CumulativeLast() external view returns (uint);
    function kLast() external view returns (uint);

    function mint(address to) external returns (uint liquidity);
    function burn(address to) external returns (uint amount0, uint amount1);
    function swap(uint amount0Out, uint amount1Out, address to, bytes calldata data) external;
    function skim(address to) external;
    function sync() external;

    function initialize(address, address) external;
}
```