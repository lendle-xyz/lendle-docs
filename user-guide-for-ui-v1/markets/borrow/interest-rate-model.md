# Interest Rate Model

Lendle uses Aave's core contracts for its lending markets.\
\
Aave’s interest rate strategy is calibrated to manage liquidity risk and optimise utilisation. The borrow interest rates come from the [Utilisation Rate](broken-reference) $$U$$.

$$U$$is an indicator of the availability of capital in the pool. The interest rate model is used to manage liquidity risk through user incentives to support liquidity:

* When capital is available: low interest rates to encourage loans.
* When capital is scarce: high interest rates to encourage repayments of loans and additional deposits.

To retrieve the interest rate strategy contract on-chain, see [this section of the developer docs](https://docs.aave.com/developers/the-core-protocol/lendingpool#getreservedata).

### Interest Rate Model

Liquidity risk materialises when utilisation is high, it becomes more problematic as $$U$$ gets closer to 100%. To tailor the model to this constraint, the interest rate curve is split in two parts around an optimal utilisation rate $$U_{optimal}$$. Before  $$U_{optimal}$$the slope is small, after it starts rising sharply.&#x20;

The interest rate$$R_t$$follows the model:

$$if \hspace{1mm} U < U_{optimal}:  \hspace{1cm}  R_t = R_0 + \frac{U_t}{U_{optimal}} R_{slope1}$$  &#x20;

$$if \hspace{1mm} U \geq  U_{optimal}:  \hspace{1cm} R_t = R_0 + R_{slope1} + \frac{U_t-U_{optimal}}{1-U_{optimal}}R_{slope2}$$



In the borrow rate technical implementation, the [calculateCompoundedInterest](https://github.com/aave/protocol-v2/blob/baeb455fad42d3160d571bd8d3a795948b72dd85/contracts/protocol/libraries/math/MathUtils.sol#L45) method relies on an approximation that mostly affects high interest rates. The resulting actual borrow rate can be:

&#x20;$$Actual APY = (1+Theoretical APY/secsperyear)^{secsperyear}-1$$

Both the variable and stable interest models, are derived from the formula above which is derived from Aave [Whitepaper](https://github.com/aave/aave-protocol/blob/master/docs/Aave_Protocol_Whitepaper_v1_0.pdf) with different parameters for each asset.

* When $$U < U_{optimal}$$ the borrow interest rates increase slowly with utilisation
* When $$U \geq  U_{optimal}$$ the borrow interest rates increase sharply with utilisation to above 50% APY if the liquidity is fully utilised.

Variable loans see their rate constantly evolving with utilisation. This means they are not ideal for financial planning.

Hence Lendle offers stable loans, that maintain their interest rate at issuance until the specific rebalancing conditions are met. For rebalancing the stable rate down, the loan stable rate$$S$$needs to be greater than the current stable rate$$S_t$$ plus a delta equal to 20%: $$S \geq S_t + 20\%$$.

For rebalancing the stable rate up, these two conditions need to be met:

1. Utilisation Rate: $$U_t > 95\%$$&#x20;
2. Overall Borrow Rate, the weighted average of all the borrow rates: $$R_O < 25\%$$&#x20;



### Variable Interest Rate Model Parameters

TBA\


### Stable Interest Rate Model Parameters

TBA\


### Interest Rate Curves

TBA\


[mantle-contracts.md](../../../contracts-and-security/mantle-contracts.md "mention")
