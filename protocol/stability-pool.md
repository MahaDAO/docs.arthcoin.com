---
description: >-
  The stability pool acts as a strong mechanism to substantially support the
  protocol by providing incentives to pooled users
---

# Stability Pool

To avoid the protocol going into extreme stress, the stability pool acts as a source of liquidity to repay debt from liquidated loans to ensure that the total `ARTH` supply always remains backed by collateral.&#x20;

When a loan position is liquidated, an equivalent amount of `ARTH` corresponding to the remaining debt has to be burned from the Stability Pool’s balance to repay its debt. In exchange, the entire collateral (committed by the borrower) is transferred to the stability pool as rewards to stability providers.

Any user may deposit `ARTH` tokens to the Stability Pool. This allows them to earn the collateral from the liquidated Trove. When a liquidation occurs, the liquidated debt is canceled with the same amount of `ARTH` in the Pool (which is burned as a result), and the liquidated Ether is proportionally distributed to depositors.

Stability Pool depositors can expect to earn net gains from liquidations, as in most cases, the value of the liquidated Ether will be greater than the value of the canceled debt (since a liquidated loan will likely have an [ICR](borrowing-arth.md#individual-collateralization-ratio-icr) just slightly below `110%`).

{% hint style="info" %}
The stability pool is currently deployed at&#x20;

[0x910F16455E5eB4605Fe639e2846579c228eeD3B5](https://etherscan.io/address/0x67002ECB9934312DF2aE28fE522C72c775e952BE#code)
{% endhint %}

## MAHA Issuance to Stability Providers

Stability Providers earn `MAHA` tokens continuously over time, in proportion to the size of their deposit. This is known as “Community Issuance”, and is handled by `CommunityIssuance.sol`.

Each Stability Pool deposit is tagged with a front end tag - the Ethereum address of the front end through which the deposit was made. Stability deposits made directly with the protocol (no front end) are tagged with the zero address.

When a deposit earns `MAHA`, it is split between the depositor and the front end through which the deposit was made. Upon registering as a front end, a front end chooses a “kickback rate”: this is the percentage of `MAHA` earned by a tagged deposit, to allocate to the depositor. Thus, the total MAHA received by a depositor is the total `MAHA` earned by their deposit, multiplied by `kickbackRate`.&#x20;

The front end takes a cut of `1-kickbackRate` of the `MAHA` earned by the deposit.

## Stability Pool example

Here’s an example of the Stability Pool absorbing liquidations. The Stability Pool contains 3 depositors, A, B, and C, and the `Growth peg:USD` price is 100.

There are two loans to be liquidated, T1 and T2:

| Loans | Collateral (ETH) | Debt (ARTH) | ICR   | ETH Value | Collateral Surplus |
| ----- | ---------------- | ----------- | ----- | --------- | ------------------ |
| T1    | 1.6              | 150         | 1.066 | 160       | 10                 |
| T2    | 2.45             | 225         | 1.088 | 245       | 20                 |

Here are the deposits, before any liquidations occur:

| Depositor | Deposit | Share  |
| --------- | ------- | ------ |
| A         | 100     | 0.1667 |
| B         | 200     | 0.3333 |
| C         | 300     | 0.5    |
| **Total** | **600** | **1**  |

Now, the first liquidation T1 is absorbed by the Pool: 150 debt is canceled with 150 Pool ARTH, and its 1.6 ETH is split between depositors. We see the gains earned by A, B, and C, are in proportion to their share of the total ARTH in the Stability Pool:

| Deposit   | Debt absorbed from T1 | Deposit after | Total ETH gained | Deposit + ETH gain | Current ROI |
| --------- | --------------------- | ------------- | ---------------- | ------------------ | ----------- |
| A         | 25                    | 75            | 0.2666           | 101.666            | 0.0166      |
| B         | 50                    | 150           | 0.53333          | 203.333            | 0.0166      |
| C         | 75                    | 225           | 0.8              | 305                | 0.0166      |
| **Total** | **150**               | **450**       | **1.6**          | **610**            | **0.0166**  |

And now the second liquidation, T2, occurs: 225 debt is canceled with 225 Pool ARTH, and 2.45 ETH is split between depositors. The accumulated ETH gain includes all ETH gain from T1 and T2.

<table><thead><tr><th>Depositor</th><th>Debt absorbed from T2</th><th>Deposit after</th><th width="124">Accumulated ETH</th><th>Deposit + ETH gain</th><th>Current ROI</th></tr></thead><tbody><tr><td>A</td><td>37.5</td><td>37.5</td><td>0.675</td><td>105</td><td>0.05</td></tr><tr><td>B</td><td>75</td><td>75</td><td>1.35</td><td>210</td><td>0.05</td></tr><tr><td>C</td><td>112.5</td><td>112.5</td><td>2.025</td><td>315</td><td>0.05</td></tr><tr><td><strong>Total</strong></td><td><strong>225</strong></td><td><strong>225</strong></td><td><strong>4.05</strong></td><td><strong>630</strong></td><td><strong>0.05</strong></td></tr></tbody></table>

It’s clear that:

* Each depositor gets the same ROI from a given liquidation
* Depositors' return increases over time, as the deposits absorb liquidations with a positive collateral surplus

Eventually, a deposit can be fully “used up” in absorbing debt, and reduced to 0. This happens whenever a liquidation occurs that empties the Stability Pool. A deposit stops earning ETH gains when it has been reduced to 0.

## FAQs

### Who funds the stability pool?

The Stability Pool is funded by users who transfer their `ARTH` into the pool. These users are also known as `pooled users` or `stability providers`.

Here is an [example transaction](https://etherscan.io/tx/0xd99cbd02c5d38d092d107bafea3d7be2101c8c0f56dc4161ea6cc8b425c8ae13) of a user depositing `ARTH` into the stability pool.

### Liquidation Rewards - Why deposit into the stability pool?

Users that provide `ARTH` to the `stability pool`, do so to earn **liquidation rewards**.

Over a certain period,  the `stability pool` will lose some/part of their `ARTH` deposits, as the protocol uses the stability pool to repay bad debt from liquidated loans.&#x20;

Although, during the same instance, the pool gains a share of the liquidated collateral (committed by the borrower at the time of procuring a loan).&#x20;

As loan positions are always created at 110%+ CR and liquidated just below it, they are rationally accepted that the participants in the stability pool will always remain in a net positive position. The amount they receive from liquidated collateral will always remain more than the amount that was deducted to pay the liquidated position.

### What will happen if the collateral value is decreasing significantly?

The only time that stability pool providers can be in a net negative position is when the collateral is losing value at a significant pace. In such a case, stability pool providers can immediately withdraw the collateral received from liquidations and sell their position if they feel that the collateral's value is decreasing significantly against the USD. \


### Why should I become a Stability Pool Provider?

Stability Providers deposit `ARTH` into the stability pool, which acts as a supplement to the Loan platform. Depositing `ARTH` valuecoin to the [Stability Pool](stability-pool.md) earns you liquidation rewards.

Whenever a loan position is liquidated, the collateral used to fund the loan (at `110%`), is returned to the Stability Pool. Stability Providers always remain in a safe and net positive position.&#x20;

### Can you give me a real-life example of how the Stability Providers benefit by funding the Stability Pool?

Liquidations happen below a 110% Collateralization Ratio.\
\
Let's take a situation where:&#x20;

* Current ARTH Pooled in the stability pool: `$1,000,000` or `500,000 ARTH` (assuming `1 $ARTH = 2 USD`)&#x20;
* You deposit `$100,000` or `50,000 ARTH`&#x20;
* Thus, you have a 10% stake in the Stability Pool
* A loan position of `$200,000` gets liquidated at `109%` collateral Ratio
* `Collateral liquidated = Loan taken out * CR% / Current Price of ETH` ie, `($200,000` `* 109%/3000) =`` `**`72.66 ETH`** &#x20;

What do you pay:

* Given that your pool share is 10%, your `ARTH` deposit will go down by 10% (the `ARTH` you added into the Stability Pool is used to settle the debt into the system) of the liquidated debt&#x20;
  * Total Debt to be settled = `200,000 USD`
  * Your Debt Share = 10%&#x20;
  * Your Debt share = `20,000 USD` (10% of Total Debt)
  * Your initial ARTH position: `100,000 USD`
  * Your new ARTH position: `80,000 USD` (Initial Position - Your Debt Share) .

What do you get:

* In return, you will gain 10% of the liquidated collateral (`72.66 ETH`), i.e. **`7.26 ETH`**, which is currently worth `$21,780` (`Current ETH price: $3000`). Your net gain from the liquidation is `$1,780 USD`&#x20;

{% hint style="info" %}
Note that depositors can immediately withdraw the collateral received from liquidations and sell it to reduce their `ETH` exposure, if the USD value of `ETH` is expected to decrease even further.&#x20;
{% endhint %}
