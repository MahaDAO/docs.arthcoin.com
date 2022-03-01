# Liquidations

When a borrower's loan falls below the minimum collateralization ratio of 110%, the user is exposed to liquidation.

**For example:**&#x20;

* A borrower took out a loan of $10,000 by committing collateral in WETH with a CR% of 120%.&#x20;
* The borrower committed 4 WETH, taking WETH at a price of $3,000`($10,000*120%/3000)`
* For the loan position to be eligible for liquidation, the CR% needs to go below 110%&#x20;
* If the price of WETH fell by 10% ($2700), his current CR% will fall to 108% ($2700\*4 WETH = $10,800 or 108% Collateralization Ratio)
* This loan position can then be liquidated by anybody &#x20;

### Post Liquidation

The loan position debt  is fulfilled by the stability pool and its collateral is distributed among stability providers.

The borrower still keeps the loan amount he received in ARTH but the user loses approximately 10% in overall value for each liquidation + fees while repaying the borrowed loan.\
\
**In the next section, learn how liquidations affect the Stability Pool rewards in favour of the Stability Pool providers.**

## **FAQs**

### Who can liquidate a loan position?&#x20;

Almost anybody can liquidate a loan position.&#x20;

The requirement to liquidate a loan position is simply:&#x20;

`Current Collateralization Ratio < Minimum Collateralization Ratio`&#x20;

* Minimum Collateralization Ratio in **Normal mode**: 110%&#x20;
* Minimum Collateralization Ratio in **Recovery mode**: 150%&#x20;

### What do I get if I liquidate a loan position?

For every liquidation, the liquidator will have to pay gas fees. To make sure, liquidations are profitable, a significant gas fee is kept aside at the time of borrowing a loan.&#x20;

Currently, the gas fee compensation is set at 5 ARTH or $10 acc to the current GMU of $2.
