# Liquidations & Flashloans

Liquidations serve as a safety mechanism in DeFi platforms like Lendle by ensuring that borrowers maintain sufficient collateral to cover their loans. They help to protect the interests of lenders and maintain the stability and integrity of the lending protocols. Liquidators play an important role in this process by actively monitoring the system and participating in profitable liquidation opportunities.

To make sure your assets are not at risk, the Lendle market works with a [health-factor.md](health-factor.md "mention") to indicate the Health of your borrow positions. When this Health Factor is reduced to 1 or less, the collateral is at risk of liquidation. \
\
An example of a liquidation scenario:\
&#xNAN;_&#x41;lice deposits 1000 USDC and borrows 500 USDC worth of DAI. If Alice's Health Factor drops below 1, her loan will be eligible for liquidation. A liquidator can repay up to 50% of a single borrowed amount (in this case, 250 USDC worth of DAI). In return, the liquidator can claim a single collateral, which is USDC, at a 10% bonus. The liquidator claims 250 + 25 USDC for repaying Alice's bad debt (250 USDC worth of DAI). 25 USDC is claimed by the protocol at a 10% bonus (20% total penalty). After liquidation, Alice has 725 USDC (1000 - 250 - 25  USDC) of supplied USDC collateral and 250 USDC worth of DAI borrowed._

It's important to note that liquidation can be a complex process, and there are risks involved for both borrowers and liquidators. For example, borrowers face the risk of losing their collateral if it is seized and sold off at a lower price, while liquidators take on the risk of market volatility and the potential for unsuccessful liquidations.

### Oracles

Oracles are a vital part of a lending market as they provide up-to-date price data of the assets on the Lendle markets. Lendle obtains its price feeds from [Pyth](https://pyth.network/price-feeds) for most of its money markets and from [API3](https://api3.org/)  for the mETH market.

### Flash Loans

Flash loans are a unique feature in decentralized finance (DeFi) that allows users to borrow a certain amount of cryptocurrency without requiring collateral, as long as the loan is repaid within the same transaction. Flash loans are made possible by the composability and programmability of smart contracts in the Ethereum Virtual Machine (EVM).\


Here's how flash loans typically work:

**Borrowing**: A user initiates a flash loan by executing a transaction that specifies the desired amount of cryptocurrency they want to borrow towards the L2Pool contract \[liquidationCall()]. This amount is typically limited by the liquidity available in the lending pool.

**Execution**: Once the loan is approved, the borrowed funds are instantly transferred to the user's wallet. At this point, the user can perform various operations with the borrowed funds within the same transaction.

**Arbitrage or Trading**: The borrower can use the borrowed funds for a wide range of purposes, such as executing arbitrage opportunities, trading on decentralized exchanges, providing liquidity, or participating in other DeFi protocols.

**Repayment**: The borrowed amount, plus any accrued interest or fees, must be repaid before the end of the transaction. If the borrower fails to repay the loan within the same transaction, the entire transaction is reversed, and the loan is considered invalid.\


The **key** aspect of flash loans is that they **must** be executed within a single transaction. If the borrowed funds are **not** returned in the same transaction, the entire transaction is **reverted**, and no funds are transferred.

Flash loans can be a powerful tool for experienced DeFi users as they allow for the execution of complex trading strategies without requiring substantial upfront capital. They provide arbitrage opportunities, taking advantage of price discrepancies across different markets, and can contribute to improving market efficiency. However, they also carry risks, including the possibility of losses if the borrowed funds are mismanaged or if the transactions executed within the loan fail to yield the expected results. That's why, typically, you'll only see developers or advanced DeFi users make use of this feature.



{% hint style="info" %}
To learn more about Flash Loans, refer to the official Aave [documentation](https://docs.aave.com/developers/v/2.0/guides/flash-loans).\
\
If you need more info on setting up a Liquidator bot for Mantle, reach out to the team through Discord.
{% endhint %}

### Lendle Market Penalty & Risk Parameters

These parameters will be updated continuously while we monitor total liquidity and health on the Mantle Chain.

<table data-full-width="true"><thead><tr><th>Asset</th><th>LTV</th><th>Liquidation Threshold</th><th>Liquidation Penalty</th></tr></thead><tbody><tr><td>WMNT</td><td>70%</td><td>75%</td><td>10%</td></tr><tr><td>USDT</td><td>80%</td><td>85%</td><td>7%</td></tr><tr><td>USDC</td><td>80%</td><td>85%</td><td>7%</td></tr><tr><td>WETH</td><td>82.5%</td><td>86%</td><td>10%</td></tr><tr><td>WBTC</td><td>40%</td><td>60%</td><td>15%</td></tr></tbody></table>
