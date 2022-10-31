# Rage Trade contest details

- 50,000 USDC main award pot
- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)
- Starts October 31, 2022 15:00 UTC
- Ends November 14, 2022 15:00 UTC

# Resources

- [Website](https://www.rage.trade/)
- [Twitter](https://twitter.com/rage_trade)
- [GitHub](https://github.com/RageTrade)
- [Medium](https://medium.com/@ragetrade)

# On-chain context

```
ERC20: WBTC, WETH, USDC, aUSDC (Aave USDC supply token) and sGLP (GMX staked GLP token)
ERC721: None
```

# Audit scope

The following contracts in the [RageTrade/delta-neutral-gmx-vaults @ 8bea1afbe746387b1a66ea9357bd41fb1c74830b](https://github.com/RageTrade/delta-neutral-gmx-vaults/tree/8bea1afbe746387b1a66ea9357bd41fb1c74830b) repo are in scope.

- `ERC4626/ERC4626Upgradeable.sol`
- `libraries/DnGmxJuniorVaultManager.sol`
- `libraries/FeeSplitStrategy.sol`
- `libraries/SafeCast.sol`
- `periphery/WithdrawPeriphery.sol`
- `vaults/DnGmxBatchingManager.sol`
- `vaults/DnGmxJuniorVault.sol`
- `vaults/DnGmxSeniorVault.sol`

# About RageTrade DN LB Vault

> source: [Delta Neutral Vault Docs](https://docs.google.com/document/d/1qapt5qKSMT7YUGfO9DK0ju0hsP0OFqxH9Ne300-UTgw/edit?usp=sharing)

RageTrade's DN LB Vaults are set of contracts that allow any users to pool in funds for providing liquidity on GMX in a delta neutral way while earning ETH rewards on GMX. This vault operates on-chain for minimizing exposure on ETH and BTC by performing a short on AAVE + Uniswap.

DeFi Protocols used:
- GMX (for liquidity provision)
- AAVE (for borrowing assets to short)
- Balancer (for flashloans to leverage AAVE borrow)
- Uniswap (for swapping)

## Steps to run the tests:

Node v16, Hardhat v2.11

1. Clone the repo
2. `yarn install`
3. `yarn patch-package`
4. Create .env file with env var `ALCHEMY_KEY` (use http://alchemy.com)
5. `yarn test`
