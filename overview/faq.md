---
description: Most frequently asked questions in the Discord will be found here
---

# FAQ

### How do I connect to Lendle?

Connecting to [Lendle.xyz](https://lendle.xyz) can be done through an EVM wallet like [MetaMask](https://metamask.io/) or [Rabby](https://rabby.io). Once you've installed and setup your wallet, you'll need to add the Mantle RPC. These can be found in the official Mantle [docs](https://docs.mantle.xyz/), or on [Chainlist](https://chainlist.org), as seen below. \
If you need a step-by-step guide on how to add a custom RPC, take a look at the [docs ](https://support.metamask.io/hc/en-us/articles/360043227612-How-to-add-a-custom-network-RPC)from MetaMask.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

### Is the code audited?

The code for our V1 lendle.xyz application is a straight-up fork from Geist, configured by our devs. Geist code has been audited by [solidity finance](https://solidity.finance/audits/GeistProtocol/) and has secured over $2 billion in TVL. \
\
Our audit is complete, and has been done by the same party that auditted the Geist code. \
You can find the Audit here: [audits.md](../contracts-and-security/audits.md "mention")\


### Is the team doxxed?

**Yes**, the team is a recipient of an official Mantle Foundation grant. One of the requirements is to KYC/Dox with the Mantle team.&#x20;

Next to this, the Lendle team holds plenty of AMAs and has a weekly fireside chat where you can meet up with the team.\


### My transaction failed, how come?

_**Usually,** this is because of either of the following cases:_\


**You're trying to withdraw your collateral from a market that is fully utilized.**\
\
Whenever you withdraw your assets from a market, make sure the utilisation rate is < 100%. You can check this by clicking on the market you're trying to withdraw from and scrolling down to the 'utilisation rate percentage'. If it's above 100%, all the money has been lent out, thus making withdrawals of that asset impossible until loans have been either paid off or liquidated.

**Transaction failed because of too little gas**

First and foremost, make sure your MNT balance **never** goes below 1!\
&#xNAN;_&#x4D;ost transactions cost around 0.5 MNT, so an approval and swap to get new gas would cost you almost 1._\
\
**Why is the cost this high while the wallet says it's only 0.000028?** Allow us to explain:\
\
Below an example of a claim transaction, where we vest our $LEND tokens. The Rabby wallet estimates the GAS at 0.000028.&#x20;

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

But when we go to the explorer and check our transaction, we see that we spent 0.462...&#x20;

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

The TL;DR is that your wallet can only estimate the 'L2 Txn Fee', which in this example was almost spot on, with 0.0000279303. However, we also have to pay a fee to settle the transaction on the L1, which is Ethereum. At the beginning of Q4 '23, we saw a quadrupling in the avg GWEI paid for txs on ETH, thus resulting in higher fees for these L1 settlement transactions.&#x20;

If you want to learn why the wallets can't give you an estimation including L1 fees, take a look over [here ](https://docs.mantle.xyz/network/introduction/transaction-fees-on-l2)in the Mantle docs where they explain the whole process in detail.\


### My claimable $LEND went to 0 or the button disappeared, are my rewards gone?

In certain edge cases, it can happen that the 'Vest Lend'  button disappeared, most notably after withdrawing your collateral in full. \
Please note that your $LEND rewards have **not** disappeared and it's purely a frontend issue we're working on to resolve. Your $LEND rewards are streamed and calculated on a 'per block basis', meaning that they are still waiting for you to be claimed in the ChefIncentivesController contract. As a workaround, make sure to claim the rewards before exiting the markets. And in the case you already did so, you can either:

* Find the claim button on the manage page, _OR_
* Return the next day as some rewards will still come in after withdrawing, thus enabling/showing the button again, _OR_
* If you're really in a rush, you can call claim() anytime on the ChefIncentivesController contract through the [blockexplorer](https://explorer.mantle.xyz/address/0x79e2fd1c484EB9EE45001A98Ce31F28918F27C41/contracts?contract-tab=write-proxy#address-tabs).\




###

