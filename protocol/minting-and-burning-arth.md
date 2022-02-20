---
description: This reviews the mechanics and scenarios that involve minting and burning ARTH
---

# Minting and Burning ARTH

### When is ARTH minted?

ARTH is only minted when collateral is deposited into any one of the collateral pools. This ensures that every ARTH that is minted will always have some kind of backing to ensure its stability. ARTH is never minted freely without some kind of collateral being deposited into the protocol.

Arbitrageurs who are looking to profit from the peg activity of ARTH can do so by minting ARTH using cryptocurrency collateral whenever ARTH is trading above its target price. The extra ARTH that is minted is sold in the open market. By opening a loan and minting ARTH, arbitrageurs are making a bet that essentially ARTH will fall back to its peg and hence will look to sell the newly minted ARTH whenever it's above its peg to realize a profit.

**Example**: this [transaction](https://bscscan.com/tx/0x804ee3393802838218a091f89d3b6f0d79968e20340b5fd73afbb3265f11fd2d) shows ARTH being minted as a user deposits collateral.

### When is ARTH burnt?

ARTH is burnt whenever it is redeemed for its underlying collateral or when a user closes his loan. Since there are multiple pools, users can go to any one of the collateral pools to redeem their ARTH tokens.

Arbitrageurs who are looking to profit from the peg activity of ARTH can do so by redeeming ARTH for its underlying cryptocurrency collateral whenever it is trading below its target price.&#x20;

**Example**: this [transaction](https://bscscan.com/tx/0x4f267cd3901155b91e35ad3b541784edf9f7bb286360919d017427ed6f809ac4) shows ARTH being burnt as it gets redeemed for it's underlying collateral.
