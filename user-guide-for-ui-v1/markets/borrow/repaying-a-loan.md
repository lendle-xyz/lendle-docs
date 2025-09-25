---
description: Unwinding your positions
---

# Repaying a loan

Repaying your loan can be done from the [dashboard.md](../../dashboard.md "mention")\
\
In this tutorial we will unwind the positions that we've created by following [how-to-deposit.md](../deposit/how-to-deposit.md "mention") & [how-to-borrow.md](how-to-borrow.md "mention")\


Head over to the Dashboard of Lendle:

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

On the right, we can see all our borrows, in this case, ETH. Click on Repay to start the process.\
\


<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

In this screen, you can see the amount of WETH we have borrowed. The amount we have to repay is higher than what we borrowed, this is because of the interest we owe to the protocol.\
In this example, I want to remove the deposited DAI in the end, so I have to repay the whole loan.\
By pressing MAX we will see the full amount we owe. Press Continue to start repaying.



<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

Verify the amount we're about to return to the protocol and take note of the new [health-factor.md](health-factor.md "mention")

When you are ready, press Approve and use default again in your MetaMask to only allow spending for the amount you put in.\
\
Then press Repay and sign the tx again. \
\
Success! You've now repaid your loan.



_Note:_

Sometimes your loan will not be paid off in full. This is because during the time you started to repay and the time the funds were received, another epoch happened and thus more money is owed to the protocol.\
\
It will look something like this:\
\


<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

By pressing MAX again you will see the exact amount you owe the protocol. \
Go through the process again to repay, until you have 0 borrow open on the [dashboard.md](../../dashboard.md "mention")\
For this example, it took 4 transactions to repay the loan in full.
