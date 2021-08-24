# Router01

### Code

[`PancakeRouter.sol`](https://github.com/BBT-DeFi/BBT-Swap/blob/main/periphery/contracts/PancakeRouter.sol)

### Address

~~IPancakeRouter01\(file name edit\)~~ is deployed at ~~**addressNumber\(number edit\)**~~ on the bitkub smart chain testnet.

## Read-Only Functions

### factory

```javascript
function factory() external pure returns (address);
```

 Returns ~~**factory address.\(link edit\)**~~

### WETH

```javascript
function WETH() external pure returns (address);
```

--------------------

## State-Changing Functions

### addLiquidity

```javascript
function addLiquidity(
        address tokenA,
        address tokenB,
        uint amountADesired,
        uint amountBDesired,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB, uint liquidity);
```

Add liquidity to an KAP20⇄KAP20 pool.

| **Name** | Type |  |
| :--- | :--- | :--- |
| tokenA | `address` | A pool token. |
| tokenB | `address` | A ppol token. |
| amountADesired | `uint` | The amount of tokenA to add as liquidity if the B/A price is &lt;= amountBDesired/amountADesired \(A depreciates\). |
| amountBDesired | `uint` | The amount of tokenB to add as liquidity if the A/B price is &lt;= amountADesired/amountBDesired \(B depreciates\). |
| amountAMin | `uint` | Bounds the extent to which the B/A price can go up before the transaction reverts. Must be &lt;= amountADesired. |
| amountBMin | `uint` | Bounds the extent to which the A/B price can go up before the transaction reverts. Must be &lt;= amountBDesired. |
| to | `address` | Recipient of the liquidity tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amountA | `uint` | The amount of tokenA sent to the pool. |
| amountB | `uint` | The amount of tokenB sent to the pool. |
| liquidity | `uint` | The amount of liquidity tokens minted. |

### addLiquidityETH

```javascript
function addLiquidityETH(
        address token,
        uint amountTokenDesired,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external payable returns (uint amountToken, uint amountETH, uint liquidity);
```

Adds liquidity to an KAP20⇄WETH pool with ETH.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | A pool token. |
| amountTokenDesired | `uint` |  The amount of token to add as liquidity if the WETH/token price is amountTokenDesired \(token depreciates\). |
| amountTokenMin | `uint` | Bounds the extent to which the WETH/token price can go up before the transaction reverts. Must be &lt;= amountTokenDesired. |
| amountETHMin | `uint` |  Bounds the extent to which the token/WETH price can go up before the transaction reverts. |
| to | `address` | Recipient of the liquidity tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amountToken | `uint` | The amount of token sent to the pool. |
| amountETH | `uint` | The amount of ETH converted to WETH and sent to the pool. |
| liquidity | `uint` | The amount of liquidity tokens minted. |

### removeLiquidity

```javascript
function removeLiquidity(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB);
```

Removes liquidity from an  KAP20⇄KAP20 pool.

| Name | Type |  |
| :--- | :--- | :--- |
| tokenA | `address` | A pool token. |
| tokenB | `address` | A pool token. |
| liquidity | `uint` | The amount of liquidity tokens to remove. |
| amountAmin | `uint` | The minimum amount of tokenA that must be received for the transaction not to revert. |
| amountBmin | `uint` | The minimum amount of tokenB that must be received for the transaction not to revert. |
| to | `address` | Recipient of the underlying assets. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amountA | `uint` | The amount of tokenA received. |
| amountB | `uint` | The amount of tokenB received. |

### removeLiquidityETH

```javascript
function removeLiquidityETH(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external returns (uint amountToken, uint amountETH);
```

Removes liquidity from an KAP20⇄WETH pool and receive ~~ETH~~.

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | A pool token. |
| liquidity | `uint` | The amount of liquidity tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of token that must be received for the transaction not to revert. |
| amountETHMin | `uint` | The minimum amount of ETH that must be received for the transaction not to revert. |
| to | `address` | Recipient of the underlying assets. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amountToken | `uint` | The amount of token received. |
| amountETH | `uint` | The amount of ETH received. |

### removeLiquidityWithPermit

```javascript
function removeLiquidityWithPermit(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountA, uint amountB);
```

 Removes liquidity from an KAP20⇄KAP20 pool without pre-approval, thanks to ~~**permit**~~.\(edit link\)

| Name | Type |  |
| :--- | :--- | :--- |
| tokenA | `address` | A pool token. |
| tokenB | `address` | A pool token. |
| liquidity | `uint` | The amount of liquidity tokens to remove. |
| amountAMin | `uint` | The minimum amount of tokenA that must be received for the transaction not to revert |
| amountBMin | `uint` | The minimum amount of tokenB that must be received for the transaction not to revert. |
| to | `address` | Recipient of the underlying assets. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
| approveMax | `bool` |  Whether or not the approval amount in the signature is for liquidity or `uint(-1)`. |
| v | `uint8` | The v component of the permit signature. |
| r | `bytes32` | The r component of the permit signature. |
| s | `bytes32` | The s component of the permit signature. |
|  |  |  |
| amountA | `uint` | The amount of tokenA received. |
| amountB | `uint` | The amount of tokenB received. |

### removeLiquidityETHWithPermit

```javascript
function removeLiquidityETHWithPermit(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountToken, uint amountETH);
```

 Removes liquidity from an KAP20⇄~~WETTH~~ pool and receive ~~ETH~~ without pre-approval, thanks to ~~**permit.\(edit link\)**~~

| Name | Type |  |
| :--- | :--- | :--- |
| token | `address` | A pool token. |
| liquidity | `uint` | The amount of liquidity tokens to remove. |
| amountTokenMin | `uint` | The minimum amount of token that must be received for the transaction not to revert. |
| amountETHMin | `uint` | The minimum amount of ETH that must be received for the transaction not to revert. |
| to | `address` | Recipient of the underlying assets. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
| approveMax | `bool` | Whether or not the approval amount in the signature is for liquidity or `uint(-1)`. |
| v | `uint8` | The v component of the permit signature. |
| r | `uint32` | The r component of the permit signature. |
| s | `uint32` | The s component of the permit signature. |
|  |  |  |
| amountToken | `uint` | The amount of token received. |
| amountETH | `uint` | The amount of ETH received. |

### swapExactTokensForTokens

```javascript
function swapExactTokensForTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
```

Swaps an exact amount of input tokens for as many output tokens as possible, along the route determined by the path. The first element of path is the input token, the last is the output token, and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

* `msg.sender` should have already given the router an allowance of at least amountIn on the input token.

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | The amount of output tokens to receive. |
| amountOutMin | `uint` | The maximum amount of input tokens that can be required before the transaction reverts. |
| path | `address[ ] calldata` |  An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of the output tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### swapTokensForExactTokens

```javascript
function swapTokensForExactTokens(
        uint amountOut,
        uint amountInMax,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
```

Receive an exact amount of output tokens for as few input tokens as possible, along the route determined by the path. The first element of path is the input token, the last is the output token, and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

* `msg.sender` should have already given the router an allowance of at least amountInMax on the input token.

| Name | Type |  |
| :--- | :--- | :--- |
| amountOut | `uint` | The amount of output tokens to receive. |
| amountInMax | `uint` | The maximum amount of input tokens that can be required before the transaction reverts. |
| path | `address[ ] calldata` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of the output tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### swapExactETHForTokens

```javascript
function swapExactETHForTokens(uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);
```

 Swaps an exact amount of ~~ETH~~ for as many output tokens as possible, along the route determined by the path. The first element of path must be ~~WETH\(edit link\)~~, the last is the output token, and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

| Name | Type |  |
| :--- | :--- | :--- |
| `msg.value` \(amountIn\) | `uint` | The amount of ~~ETH~~ to send. |
| amountOutMin | `uint` | The minimum amount of output tokens that must be received for the transaction not to revert. |
| path | `adress[ ] calldata` |  An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of the output tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### swapTokensForExactETH

```javascript
function swapTokensForExactETH(uint amountOut, uint amountInMax, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
```

Receive an exact amount of ~~ETH~~ for as few input tokens as possible, along the route determined by the path. The first element of path is the input token, the last must be ~~WETH\(edit link\)~~, and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

* `msg.sender` should have already given the router an allowance of at least amountInMax on the input token.
* If the to address is a smart contract, it must have the ability to receive ~~ETH~~.

| Name | Type |  |
| :--- | :--- | :--- |
| amountOut | `uint` | The amount of ~~ETH~~ to receive. |
| amountInMax | `uint` | The maximum amount of input tokens that can be required before the transaction reverts. |
| path | `address[ ] calldata` | An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of ~~ETH~~. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### swapExactTokensForETH

```javascript
 function swapExactTokensForETH(uint amountIn, uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
```

Swaps an exact amount of tokens for as much ~~ETH~~ as possible, along the route determined by the path. The first element of path is the input token, the last must be ~~WETH~~, and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

* If the to address is a smart contract, it must have the ability to receive ~~ETH.~~

| Name | Type |  |
| :--- | :--- | :--- |
| amountIn | `uint` | The amount of input tokens to send. |
| amountOutMin | `uint` | The minimum amount of output tokens that must be received for the transaction not to revert. |
| path | `address[ ] calldata` |  An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of the ~~ETH.~~ |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### swapETHForExactTokens

```javascript
function swapETHForExactTokens(uint amountOut, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);
```

Receive an exact amount of tokens for as little ~~ETH~~ as possible, along the route determined by the path. The first element of path must be ~~WETH\(edit link\)~~, the last is the output token and any intermediate elements represent intermediate pairs to trade through \(if, for example, a direct pair does not exist\).

* Leftover ~~ETH~~, if any, is returned to `msg.sender`.

| Name | Type |  |
| :--- | :--- | :--- |
| amountOut | `uint` | The amount of tokens to receive. |
| `msg.value` \(amountInMax\) | `uint` | The maximum amount of ETH that can be required before the transaction reverts. |
| path | `address[ ] calldata` |  An array of token addresses. `path.length` must be &gt;= 2. Pools for each consecutive pair of addresses must exist and have liquidity. |
| to | `address` | Recipient of the output tokens. |
| deadline | `uint` | Unix timestamp after which the transaction will revert. |
|  |  |  |
| amounts | `uint[ ] memory` | The input token amount and all subsequent output token amounts. |

### quote

See ~~**quote.**~~

### getAmountOut

See getAmountOut.

### getAmountIn

~~See getAmountIn.~~

### getAmountsOut

```javascript
function getAmountsOut(uint amountIn, address[] calldata path) external view returns (uint[] memory amounts);
```

See getAomuntsOut.

### getAmountsIn

```javascript
function getAmountsIn(uint amountOut, address[] calldata path) external view returns (uint[] memory amounts);
```

See getAmountsIn

## Interface

```javascript
import '@uniswap/v2-core/contracts/interfaces/IPancakeFactory.sol';
```

```javascript
pragma solidity >=0.6.2;

interface IPancakeRouter01 {
    function factory() external pure returns (address);
    function WETH() external pure returns (address);

    function addLiquidity(
        address tokenA,
        address tokenB,
        uint amountADesired,
        uint amountBDesired,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB, uint liquidity);
    function addLiquidityETH(
        address token,
        uint amountTokenDesired,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external payable returns (uint amountToken, uint amountETH, uint liquidity);
    function removeLiquidity(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline
    ) external returns (uint amountA, uint amountB);
    function removeLiquidityETH(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline
    ) external returns (uint amountToken, uint amountETH);
    function removeLiquidityWithPermit(
        address tokenA,
        address tokenB,
        uint liquidity,
        uint amountAMin,
        uint amountBMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountA, uint amountB);
    function removeLiquidityETHWithPermit(
        address token,
        uint liquidity,
        uint amountTokenMin,
        uint amountETHMin,
        address to,
        uint deadline,
        bool approveMax, uint8 v, bytes32 r, bytes32 s
    ) external returns (uint amountToken, uint amountETH);
    function swapExactTokensForTokens(
        uint amountIn,
        uint amountOutMin,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
    function swapTokensForExactTokens(
        uint amountOut,
        uint amountInMax,
        address[] calldata path,
        address to,
        uint deadline
    ) external returns (uint[] memory amounts);
    function swapExactETHForTokens(uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);
    function swapTokensForExactETH(uint amountOut, uint amountInMax, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
    function swapExactTokensForETH(uint amountIn, uint amountOutMin, address[] calldata path, address to, uint deadline)
        external
        returns (uint[] memory amounts);
    function swapETHForExactTokens(uint amountOut, address[] calldata path, address to, uint deadline)
        external
        payable
        returns (uint[] memory amounts);

    function quote(uint amountA, uint reserveA, uint reserveB) external pure returns (uint amountB);
    function getAmountOut(uint amountIn, uint reserveIn, uint reserveOut) external pure returns (uint amountOut);
    function getAmountIn(uint amountOut, uint reserveIn, uint reserveOut) external pure returns (uint amountIn);
    function getAmountsOut(uint amountIn, address[] calldata path) external view returns (uint[] memory amounts);
    function getAmountsIn(uint amountOut, address[] calldata path) external view returns (uint[] memory amounts);
}
```