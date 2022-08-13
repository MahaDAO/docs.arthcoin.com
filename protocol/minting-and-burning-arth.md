---
description: This reviews the mechanics and scenarios that involve minting and burning ARTH
---

# Minting and Burning

### When is ARTH Minted?

`ARTH` is minted whenever `ETH` is deposited into any of the  pools, which ensures that every `ARTH` minted will always have some kind of backing to ensure its stability. `ARTH` is never minted without some amount of `ETH` being deposited into the protocol.&#x20;

Arbitrageurs looking to profit from the peg activity of `ARTH` can mint `ARTH` using cryptocurrency collateral whenever `ARTH` is trading above its target price. The extra `ARTH` that is minted is sold in the open market. A bet is being made by arbitrageurs that `ARTH` will fall back to its peg and will look to sell the newly minted `ARTH` whenever it's above its peg to realize a profit. This is done by opening a loan and minting `ARTH`.

**Example**: this [transaction](https://etherscan.io/tx/0xcb7b4eab25c06ea759daa31700b1e1271adf7e06fa5176d6808924a1c8057faf) shows ARTH being minted as a user deposits collateral.

![https://etherscan.io/tx/0xcb7b4eab25c06ea759daa31700b1e1271adf7e06fa5176d6808924a1c8057faf](<../.gitbook/assets/image (2).png>)

{% hint style="info" %}
A minimum debt of `250 ARTH` is required to open a loan position. A user also has to set aside `50 ARTH` for gas fees in case of liquidations (also called as the liquidation reserve). This is refunded back to the user when the loan is closed.&#x20;
{% endhint %}

### When is ARTH Burnt?

`ARTH` is burnt whenever the underlying collateral is redeemed or during the closure of a loan by a user.&#x20;

This happens by market participants in three different scenarios:

* **Whenever ARTH trades below its target price:** Arbitrageurs looking to make a profit from the peg activity of ARTH can redeem ARTH for its underlying cryptocurrency collateral whenever it is trading below its target price. \
  \
  If `ARTH` trades at 1.9$ and its target price is supposed to be 2$, then `ARTH` is bought out from the open market to make redemptions from the protocol at 2$ for a profit.
* **Whenever a loan is closed or liquidated:** Whenever a loan is closed or liquidated, the ARTH that was minted against that loan is burnt off and the collateral against that loan is given back or distributed to the [stability pool depositors](stability-pool.md).
* **Whenever a loan is redeemed:** Users who redeem `ARTH` for a cryptocurrency collateral will be able to burn their `ARTH`.

**Example**: this [transaction](https://etherscan.io/tx/0x92ddd07b50e0f1778b48aea8da39fb91d8fea223dba61913c6e438b0840e3155) shows `ARTH` being burnt as it gets redeemed for its underlying collateral.&#x20;

![https://etherscan.io/tx/0x92ddd07b50e0f1778b48aea8da39fb91d8fea223dba61913c6e438b0840e3155](<../.gitbook/assets/image (14).png>)
