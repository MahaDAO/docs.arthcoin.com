# Liquidations

The protocol utilizes a two-step liquidation mechanism in the following order of priority:

1. Offset under-collateralized loans against the [Stability Pool](stability-pool.md) containing `ARTH` tokens
2. Redistribute under-collateralized loans to other borrowers if the Stability Pool is emptied

The protocol primarily uses the `ARTH` tokens in its Stability Pool to absorb the under-collateralized debt, i.e. to repay the liquidated borrower's liability.

Anybody can liquidate a loan as soon as it drops below the Minimum Collateral Ratio of `110%`. The initiator receives a gas compensation (`50 ARTH` + `0.5%` of the loan's collateral) as a reward for this service.

Post a liquidation, a loan position's debt is fulfilled by the stability pool and its collateral is distributed among [stability pool providers](stability-pool.md). The borrower still keeps the loan amount he received in `ARTH` but the user loses approximately `10%` in overall value for each liquidation + fees while repaying the borrowed loan.

{% hint style="info" %}
Liquidations are performed by the [TroveManager](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/TroveManager.sol) contract which is deployed at&#x20;

[0x8b1da95724b1e376aE49FdB67afE33Fe41093af5](https://etherscan.io/address/0x8b1da95724b1e376aE49FdB67afE33Fe41093af5#code)
{% endhint %}

{% hint style="warning" %}
In special cases when the total collateral ratio drops below `150%` and the protocol goes under the [Recovery mode](recovery-mode.md), liquidation happens to all loans below the `150%` collateral ratio until the total collateral ratio comes back to `150%`
{% endhint %}

If the liquidated debt is higher than the amount of `ARTH` in the Stability Pool, the system tries to cancel as much debt as possible with the tokens in the Stability Pool, and then redistributes the remaining liquidated collateral and debt across all active loans.

Anyone may call the public `liquidateTroves()` function, which will check for under-collateralized loans, and liquidate them. Alternatively they can call `batchLiquidateTroves()` with a custom list of trove addresses to attempt to liquidate.

## **Liquidation example**&#x20;

* A borrower took out a loan of `$10,000` by committing collateral in `ETH` with a CR of `120%`\`
* The borrower committed 4 `ETH`, taking `ETH` at a price of $3,000`($10,000*120%/3000)`
* For the loan position to be eligible for liquidation, the CR% needs to go below `110%`
* If the price of `ETH` fell by `10%` (`$2700`), his current CR% will fall to `108%` (`$2700*4 ETH` = `$10,800` or `108%` Collateralization Ratio)
* Anybody can then liquidate this loan position

This [transaction](https://etherscan.io/tx/0xca4263fe02d5725dbb345991b7f66885bc0dbb10d9fb01c82184e63addf00a3c) showcases a liquidation event that rewarded the liquidator with `50 ARTH + 0.5% of the collateral` and sent the `ETH` rewards to `ARTH` stakers in the stability pool.

![https://etherscan.io/tx/0xca4263fe02d5725dbb345991b7f66885bc0dbb10d9fb01c82184e63addf00a3c](<../.gitbook/assets/image (101).png>)

## Liquidation Logic

To understand what exactly happens in normal mode and in recovery mode, we detail below the precise behavior of liquidations, which depends on the ICR of the Trove being liquidated and global system conditions: the total collateralization ratio (TCR) of the system, the size of the Stability Pool, etc.

* ICR = [Individual Collateral Ratio](borrowing-arth.md#individual-collateral-ratio-icr)
* MCR = [Minimum Collateral Ratio ](borrowing-arth.md#minimum-collateralization-ratio-mcr)
* TCR = [Total Collateral Ratio ](borrowing-arth.md#total-collateral-ratio-tcr)

### Normal Mode Liquidations (TCR > 150%)

| Condition                                                                                                        | Liquidation behavior                                                                                                                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><code>ICR &#x3C; MCR</code> <strong>and</strong> </p><p><code>Stability Pool ARTH</code> >= loan debt</p>     | <p>ARTH in the StabilityPool equal to the Trove's debt is offset with the Trove's debt. </p><p></p><p>The Trove's ETH collateral is shared between depositors.</p>                                                                                                                                                                    |
| <p><code>ICR &#x3C; MCR</code> <strong>and</strong> </p><p><code>Stability Pool ARTH</code> &#x3C; loan debt</p> | <p>The total StabilityPool ARTH is offset with an equal amount of debt from the loan. A fraction of the loan's collateral (equal to the ratio of its offset debt to its entire debt) is shared between depositors. </p><p></p><p>The remaining debt and collateral (minus ETH gas compensation) is redistributed to active loans.</p> |
| <p><code>ICR &#x3C; MCR</code> <strong>and</strong> </p><p><code>Stability Pool ARTH</code> = 0</p>              | Redistribute all debt and collateral (minus ETH gas compensation) to active loans.                                                                                                                                                                                                                                                    |
| `ICR >= MCR`                                                                                                     | Do nothing.                                                                                                                                                                                                                                                                                                                           |

### Recovery Mode Liquidations (TCR < 150%)

In a special scenario when the protocol goes into [Recovery Mode](recovery-mode.md), liquidations handled by the protocol behave differently. This section describes all the various scenarios on when/how a liquidation happens.

| Condition                                                                                                                 | Behaviour                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ICR <=100%`                                                                                                              | Redistribute all debt and collateral (minus `ETH` gas compensation) to active loans.                                                                                                                                                                                                                                                                                                                                                                                                                       |
| <p><code>100% &#x3C; ICR &#x3C; MCR</code> <strong>and</strong> <br><code>Stability Pool ARTH > Loan debt</code></p>      | `ARTH` in the Stability Pool equal to the loan's debt is offset with the loan's debt. The loan's `ETH` collateral (minus `ETH` gas compensation) is shared between depositors.                                                                                                                                                                                                                                                                                                                             |
| <p><code>100% &#x3C; ICR &#x3C; MCR</code> <strong>and</strong> <br><code>Stability Pool ARTH &#x3C; Loan debt</code></p> | <p>The total Stability Pool <code>ARTH</code> is offset with an equal amount of debt from the loan. A fraction of the loan's collateral (equal to the ratio of its offset debt to its entire debt) is shared between depositors. <br><br>The remaining debt and collateral (minus <code>ETH</code> gas compensation) is redistributed to all remaining active loans.</p>                                                                                                                                   |
| <p><code>MCR &#x3C;= ICR &#x3C; 150%</code> <strong>and</strong> </p><p><code>Stability Pool ARTH >= Loan debt</code></p> | <p>The Stability Pool <code>ARTH</code> is offset with an equal amount of debt from the Trove. </p><p></p><p>A fraction of <code>ETH</code> collateral with dollar value equal to <code>1.1 * debt</code> is shared between depositors. Nothing is redistributed to other active loans. </p><p></p><p>Since its <code>ICR</code> was <code>> 1.1</code>, the Trove has a collateral remainder, which is sent to the <code>CollSurplusPool</code> and is claimable by the borrower. The loan is closed.</p> |
| `MCR <= ICR < 150%` **and** `Stability Pool ARTH < Trove debt`                                                            | Nothing Happens                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `ICR >= 150%`                                                                                                             | Nothing Happens                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

## **FAQs**

### Who can liquidate a loan position?&#x20;

Almost anybody can liquidate a loan position. The requirement to liquidate a loan position is simply:&#x20;

`Current Collateralization Ratio < Minimum Collateralization Ratio`&#x20;

* Minimum Collateralization Ratio in **Normal mode**: `110%`
* Minimum Collateralization Ratio in **Recovery mode**: `150%`

### What do I get if I liquidate a loan position?

For every liquidation, the liquidator will have to pay gas fees. To make sure, liquidations are profitable, a significant gas fee is kept aside at the time of borrowing a loan.&#x20;

Currently, the gas fee compensation is set at `50 ARTH`.

Besides the gas fee compensation, the liquidator also earns `0.5%` of the liquidated loan's collateral.

### What happens if there is no ARTH in the stability pool?

In the most extreme scenario when there is no `ARTH` in the stability pool that can be used to pay back a loan, the debt & the collateral is redistributed across all the loan holders.&#x20;

In such a case, the system redistributes the debt and collateral from liquidated loans to all other existing loans. The redistribution of debt and collateral is done in proportion to the recipient loan's collateral amount

