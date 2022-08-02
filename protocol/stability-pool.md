---
description: >-
  The stability pool acts as a strong mechanism to substantially support the
  protocol by providing incentives to pooled users
---

# Stability Pools

To avoid the protocol going into extreme stress, the stability pool acts as a source of liquidity to repay debt from liquidated loans to ensure that the total ARTH supply always remains backed by collateral.&#x20;

When a loan position is liquidated, an equivalent amount of ARTH corresponding to the remaining debt has to be burned from the Stability Pool’s balance to repay its debt. In exchange, the entire collateral (committed by the borrower) is transferred to the stability pool as rewards to stability providers.

{% hint style="info" %}
The stability is currently deployed at [0x2c360b513ae52947eeb37cfad57ac9b7c9373e1b](https://etherscan.io/address/0x2c360b513ae52947eeb37cfad57ac9b7c9373e1b)
{% endhint %}

### Who funds the stability pool?

The Stability Pool is funded by users transferring their ARTH into the pool. These are also known as pooled users or stability providers.

### Why do users add funds to the stability pool?

Users that provide ARTH to the stability pool, do so to earn liquidation rewards.

Over a certain period, the stability pool will lose some/part of their ARTH deposits, as the protocol uses the stability pool to repay debt from liquidated loans. Although, during the same instance, the pool gains share of the liquidated collateral (committed by the borrower at the time of procuring a loan).&#x20;

As loan positions are always created at 110%+ CR and liquidated just below it, they are rationally accepted that the participants in the stability pool will always remain in a net positive position. The amount they receive from liquidated collateral will always remain more than the amount that was deducted to pay the liquidated position.

### What will happen if the collateral value is decreasing significantly?

The only time that stability pool providers can be in a net negative position is when the collateral is losing value at a significant pace. In such a case, stability pool providers can immediately withdraw the collateral received from liquidations and sell their position if they feel that the collateral's value is decreasing significantly against the USD. \


## FAQs

### Why should I become a Stability Pool Provider?

Stability Providers deposit ARTH into the stability pool, which acts as a supplement to the Loan platform. Depositing ARTH valuecoin to the [Stability Pool](stability-pool.md) earns you liquidation rewards.

Whenever a loan position is liquidated, the collateral used to fund the loan (at 110%), is returned to the Stability Pool. \
\
Stability Providers always remain in a safe and net positive position.&#x20;

### Can you give me a real-life example of how the Stability Providers benefit by funding the Stability Pool?

Liquidations happen below 110% Collateralization Ratio.\
\
Let's take a situation where:&#x20;

* Current ARTH Pooled in the stability pool: $1,000,000 or 500,000 ARTH (1 $ARTH = 2 USD)&#x20;
* You deposit $100,000 or 50,000 ARTH&#x20;
* Thus, you have a 10% stake in the Stability Pool
* A loan position of $200,000 gets liquidated at 109% collateral Ratio
* Collateral liquidated = Loan taken out \* CR% / Current Price of collateral `($200,000*109%/3000) =`` `**`72.66 WETH`** &#x20;

What do you pay:&#x20;

* Given that your pool share is 10%, your ARTH deposit will go down by 10% (the ARTH you added into the Stability Pool is used to settle the debt into the system) of the liquidated debt&#x20;
  * Total Debt to be settled = 200,000 USD
  * Your Debt Share = 10%&#x20;
  * Your Debt share = 20,000 USD (10% of Total Debt)
  * Your initial ARTH position: 100,000 USD
  * Your new ARTH position: **80,000 USD** (Initial Position - Your Debt Share) .

What do you get:

* In return, you will gain 10% of the liquidated collateral(72.66 WETH), i.e. **`7.26 WETH`**, which is currently worth $21,780(Current WETH price: $3000). Your net gain from the liquidation is `$1,780 USD` &#x20;

Note that depositors can immediately withdraw the collateral received from liquidations and sell it to reduce their exposure to a volatile asset like ETH, if the USD value of ETH is expected to decrease.&#x20;
