# Liquidations

The user is exposed to liquidation when a borrower's loan falls below the minimum collateralization ratio of 110%.

**For example:**&#x20;

* A borrower took out a loan of $10,000 by committing collateral in `ETH` with a CR% of 120%
* The borrower committed 4 `ETH`, taking `ETH` at a price of $3,000`($10,000*120%/3000)`
* For the loan position to be eligible for liquidation, the CR% needs to go below 110%&#x20;
* If the price of `ETH` fell by 10% ($2700), his current CR% will fall to 108% ($2700\*4 ETH = $10,800 or 108% Collateralization Ratio)
* This loan position can then be liquidated by anybody

Anybody can liquidate a loan as soon as it drops below the Minimum Collateral Ratio of `110%`. The initiator receives a gas compensation (`5 ARTH` + `0.5%` of the Trove's collateral) as a reward for this service.

Post a liquidation, the loan position's debt is fulfilled by the stability pool and its collateral is distributed among stability providers. The borrower still keeps the loan amount he received in ARTH but the user loses approximately 10% in overall value for each liquidation + fees while repaying the borrowed loan.

In special cases when the protocol goes under the [Recovery mode](recovery-mode.md), liquidation happens to all loans below the `150%` collateral ratio.

This [transaction](https://etherscan.io/tx/0xca4263fe02d5725dbb345991b7f66885bc0dbb10d9fb01c82184e63addf00a3c) is an example of a liquidation that rewarded the liquidator with `50 ARTH` and sent the `ETH` rewards to `ARTH` stakers in the stability pool.

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

### What happens if there is no ARTH in the stability pool?

In the most extreme scenario when there is no ARTH in the stability pool that can be used to pay back a loan, the debt & the collateral is redistributed across all the loan holders.&#x20;

In such a case, the system redistributes the debt and collateral from liquidated loans to all other existing loans. The redistribution of debt and collateral is done in proportion to the recipient loan's collateral amount
