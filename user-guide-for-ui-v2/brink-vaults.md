---
description: Lendle x Brink
---

# Brink Vaults

### Vaults Overview (Powered by Brink)

Each vault on Lendle’s Earn page is backed by Brink’s on-chain vault infrastructure, built atop the ERC-4626 standard, which automates yield generation and risk-managed allocations. Depositors simply provide the underlying asset and receive a vault share token; behind the scenes, the system handles everything else.

#### Operational Workflow Highlights

1. **User Deposits** – A user deposits the underlying token (USDe, WETH, or WMNT) into the corresponding Lendle vault.
2. **Brink Engine Integration** – The deposit is directed into the Brink vault infrastructure. The “Brink Engine” takes over.&#x20;
3. **Strategy Calculation & Optimization** – The engine continuously assesses yield opportunities, risk metrics and current utilization to compute the optimal allocation strategy.&#x20;
4. **Dynamic Allocation & Rebalancing** – The system deploys (and if needed redeploys) funds into vetted DeFi protocols and markets. Rebalancing occurs frequently (hourly) to adapt to changing yield conditions and maintain capital efficiency.&#x20;
5. **Risk Management & Transparency** – Throughout the lifecycle, real-time risk assessments monitor volatility, network or protocol risk, and ensure that all smart contracts are audited and verifiable.&#x20;
6. **Withdrawal & Share Redemption** – Users can redeem their vault shares at any time and receive underlying assets plus accrued yield, while the backend manages the unwinding of the deployed positions.

***

### Vault-by-Vault Detail

#### USDe Vault&#x20;

* Underlying Asset: **USDe.**
* Mechanism: When you deposit USDe into the vault, your funds are routed by Brink into high-quality stable-asset yield markets and isolated pairs that use USDe, selecting destinations with favourable APY, low risk and adequate liquidity.
* Rebalancing Logic: The engine monitors stable-asset markets and may rotate capital when yields drop or utilization saturates a pair.
* User Benefit: You gain exposure to optimized stable-asset yield without needing to choose markets, the vault auto-compounds returns and adapts to changing conditions.

#### WETH Vault&#x20;

* Underlying Asset: **WETH.**
* Mechanism: Upon deposit, the vault hands off WETH to Brink, which then allocates across ETH-related yield sources: e.g., ETH-denominated lending pools, liquid staking derivatives, isolated pairs with ETH.
* Rebalancing Logic: The engine watches ETH yield opportunities, and dynamically moves WETH accordingly to maximize risk-adjusted return.
* User Benefit: Earn yield on your ETH exposure without manually shifting assets or managing staking, the vault handles routing to the best available strategy.

#### WMNT Vault&#x20;

* Underlying Asset: **WMNT.**&#x20;
* Mechanism: When you deposit WMNT, the vault uses Brink’s routing to deploy into Mantle-ecosystem-native yield strategies: isolated pairs that include MNT, liquidity incentives, or lending markets involving MNT.
* Rebalancing Logic: Because ecosystem incentives and yield sources vary, the engine is particularly active in rotating exposures, evaluating which MNT pairs give best yield while managing ecosystem risk.
* User Benefit: Participate passively in the Mantle network’s growth and yield opportunities via MNT, while Brink handles the technical details of strategy execution.

***

### What This Means for Users

* **Non-custodial & transparent**: You retain control of your assets, vault contracts follow ERC-4626 standards, and you can verify allocations, performance and rebalances on-chain.
* **Hands-off yield**: Deposit once into a Lendle vault and Brink takes care of deployment, optimization, and compounding.
* **Dynamic optimization**: Rather than static yield strategies, these vaults actively rotate capital based on market conditions, leveraging Brink’s real-time decision engine.
* **Risk-aware**: Through frequent on-chain monitoring and rebalancing, the system targets best returns on user's funds.
* **Composability**: Since they’re ERC-4626 vaults, these funds integrate smoothly with other DeFi protocols.
