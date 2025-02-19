---
description: Providing liquidity to the Lendle market
---

# How-To-Deposit

{% hint style="info" %}
If you haven't bridged your funds to the Mantle chain, or looking to add more from a different chain, we can recommend using the 1-click-supply through Axelar [here](https://app.lendle.xyz/bridge-supply).\
If you're just looking for a bridge, we have a couple of options [here](https://app.lendle.xyz/bridge).
{% endhint %}

In this Tutorial we will be depositing DAI through the [..](../ "mention")\


We've opened one of the markets from this screen, in this example it's DAI.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

_Under 'Reserve status & configuration' you can see:_

* _The total amount of DAI that is supplied by users_
* _The yield in APY (from protocol fees) and APR (from $LEND token)_
* _The collateral usage_&#x20;
  * _The Loan-To-Value (LTV) percentage, MAX LTV, indicates how much of your deposited DAI can be used to take a loan against_
  * _The Liquidation Threshold percentage shows the investor when the collateral becomes available for liquidation. i.e. If the outstanding loan equals or exceeds 85% of the DAI deposited, it will be liquidated._
  * _The Liquidation Penalty percentage indicates the Bounty a liquidator can get from liquidating a position on this market. The penalty is taken from the investors' collateral._

_Under 'Borrow Info' you can see:_

* _The total amount of DAI borrowed._
* _The APY for borrowing, i.e. the % on the outstanding loan you pay as interest for borrowing+ the reward APR in $LEND tokens for borrowing._

_On the right, under 'Your Info', you can see:_

* _The wallet balance in this market asset_
* _How much is available to supply and borrow_
* _2 buttons to supply and/or borrow this market's asset_

\
For the tutorial, we will click on supply which will take us to the supply screen for the DAI market:

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

_On the top you can see Your balance (any DAI that is already supplied), Your wallet balance (any DAI that is in your wallet) and your overall health factor._\
\
_There is also more info about the DAI market, like Utilization rate (how much of the supplied DAI is borrowed), the available liquidity in the market to lend out, the reward APY from protocol fees and if this asset is currently  available to be used as collateral (to borrow against)_

_Next to this we see the same information as on the previous screen, with the Maximum LTV, Liquidation Threshold and Liquidation Penalty %. We also display the Asset prize that we retrieve from our Oracle._

On the bottom we can either use MAX or input a custom number to deposit and press Continue to start the approval and deposit transactions:

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>1/3</p></figcaption></figure>

Press Approve, and press default in the MetaMask popup to approve the exact amount you are spending, which is 1000 in this example.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption><p>2/3</p></figcaption></figure>

Press Deposit, and confirm the transaction once more in MetaMask.

After a couple of seconds your screen will update (depending on RPC) and it should look something like this:

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

We can see in the Top left, that my balance has updated to 1000 and my wallet balance is now 0.\
In the bottom you can see our 2 transactions, which can be followed to the block explorer for more info.

Success! We've now supplied 1000 DAI to Lendle.\
\
The next tutorial will be [how-to-borrow.md](../borrow/how-to-borrow.md "mention")\


### Collateral

After you've deposited an asset, it will be enabled as collateral by default. A collateralised asset will activate your borrowing power and correlate with the number of loans you can make (depending on the Loan-To-Value \[LTV] settings of each market)\


You can use the toggle on each asset in the Deposit screen to disable the asset from being used as Collateral. \
\
&#xNAN;_&#x50;lease note that this will influence your Health Factor and can lead to liquidation if this drops below 1_
