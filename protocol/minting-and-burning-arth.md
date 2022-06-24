---
description: This reviews the mechanics and scenarios that involve minting and burning ARTH
---

# Minting and Burning

### When is ARTH minted?

ARTH is minted when a collateral is deposited into any of the collateral pools which ensures that every ARTH minted will always have some kind of backing to ensure its stability. ARTH is never minted without some kind of collateral being deposited into the protocol.&#x20;

Arbitrageurs looking to profit from the peg activity of ARTH can mint ARTH using cryptocurrency collateral whenever ARTH is trading above its target price. The extra ARTH that is minted is sold in the open market. A bet is being made by arbitrageurs that ARTH will fall back to its peg and will look to sell the newly minted ARTH whenever it's above its peg to realize a profit. This done by opening a loan and minting ARTH.

**Example**: this [transaction](https://bscscan.com/tx/0x89f65e57b49b58bc38ace144710f0a043a3289d5d294396db81e25ab392179fc) shows ARTH being minted as a user deposits collateral.

### When is ARTH burnt?

ARTH is burnt whenever the underlying collateral is redeemed or during the closure of a loan by a user.&#x20;

This happens by market participants in three different scenarios:

* Whenever ARTH trades below it's target price: Arbitrageurs looking to make a profit from the peg activity of ARTH can redeem ARTH for its underlying cryptocurrency collateral whenever it is trading below its target price. \
  \
  If ARTH trades at 1.9$ and it's target price is supposed to be 2$, then ARTH is bought out from the open market to make redemptions from the protocol at 2$ for a profit
* Whenever a loan is closed or liquidated: Whenever a loan is closed or liquidated, the ARTH that was minted against that loan is burnt off and the collateral against that loan is given back or distributed to the [stability pool depositors](stability-pool.md).
* Whenever a loan is redeemed: Users who redeem ARTH for a cryptocurrency collateral will get burn their ARTH.

**Example**: this [transaction](https://bscscan.com/tx/0x4f267cd3901155b91e35ad3b541784edf9f7bb286360919d017427ed6f809ac4) shows ARTH being burnt as it gets redeemed for its underlying collateral.
