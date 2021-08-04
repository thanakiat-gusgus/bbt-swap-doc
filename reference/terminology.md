# Terminology

#### Automated market maker[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#automated-market-maker)

An automated market maker is a smart contract on Ethereum that holds on-chain liquidity reserves. Users can trade against these reserves at prices set by an automated market making formula.

#### Constant product formula[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#constant-product-formula)

The automated market making algorithm used by BBTSwap. See [x\*y=k](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#x--y--k).

#### ERC20[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#erc20)

ERC20 tokens are fungibile tokens on Ethereum. Uniswap supports all standard ERC20 implementations.

#### Factory[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#factory)

A smart contract that deploys a unique smart contract for any ERC20/ERC20 trading pair.

#### Pair[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#pair)

A smart contract deployed from the ???? Factory that enables trading between two ERC20 tokens.

#### Pool[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#pool)

Liquidity within a pair is pooled across all liquidity providers.

#### Liquidity provider / LP[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#liquidity-provider--lp)

A liquidity provider is someone who deposits an equivalent value of two ERC20 tokens into the liquidity pool within a pair. Liquidity providers take on price risk and are compensated with fees.

#### Mid price[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#mid-price)

The price between what users can buy and sell tokens at a given moment. In BBTSwap this is the ratio of the two ERC20 token reserves.

#### Price impact[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#price-impact)

The difference between the mid-price and the execution price of a trade.

#### Slippage[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#slippage)

The amount the price moves in a trading pair between when a transaction is submitted and when it is executed.

#### Core[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#core)

Smart contracts that are essential for BBTSwap to exist. Upgrading to a new version of core would require a liquidity migration.

#### Periphery[\#](https://docs.uniswap.org/protocol/V2/concepts/protocol-overview/glossary#periphery)

External smart contracts that are useful, but not required for BBTSwap to exist. New periphery contracts can always be deployed without migrating liquidity.

