---
description: >-
  This section talks about how the ARTH platform changes fees to keep the
  protocol stable.
---

# Protocol Fees

Fees are charged by the protocol on various actions performed by users on the protocol. The ARTH platform charges three kinds of fees:

* Mint & Redemption Fees in `ETH` and `ARTH`
* Stability Fees in `MAHA`
* A refundable liquidation fee (also called as the liquidation reserve) in `ARTH` (currently set at `50 ARTH`)

### Stability Fee

Stability fees is a mechanism that is being used to encourage or discourage collateral redemption from within the protocol. Stability fees is charged in `MAHA` tokens and is calculated as a percentage of the collateral that is being redeemed.

`MAHA` tokens charged from the stability fee is burnt off from the supply.

When governance predicts that the protocol is at high risk of losing its collateral, it sets the stability fee at a higher percentage (from 5-20%). When governance predicts that the protocol is under low risk, then the stability fees is reduced to 0-5%.

{% hint style="info" %}
The stability fee is an extra measure to influence the redemption Behavior of ARTH but is not currently active.
{% endhint %}
