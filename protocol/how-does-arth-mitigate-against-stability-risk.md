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

## Stability Fees

Stability fees is a mechanism that is being used to encourage or discourage collateral redemption from within the protocol. Stability fees is charged in `MAHA` tokens and is calculated as a percentage of the collateral that is being redeemed.

`MAHA` tokens charged from the stability fee is burnt off from the supply.

When governance predicts that the protocol is at high risk of losing its collateral, it sets the stability fee at a higher percentage (from `5-20%`). When governance predicts that the protocol is under low risk, then the stability fees is reduced to `0-5%.`

{% hint style="info" %}
The stability fee is an extra measure to influence the redemption Behavior of ARTH but is not currently active.
{% endhint %}

## Fee Schedule

Redemption and issuance fees are based on the `baseRate` state variable in the [TroveManager](https://github.com/MahaDAO/arth-core/blob/main/packages/contracts/contracts/TroveManager.sol), which is dynamically updated. The `baseRate` increases with each redemption, and decays according to time passed since the last fee event - i.e. the last redemption or issuance of ARTH.

Upon each redemption:

* `baseRate` is decayed based on time passed since the last fee event
* `baseRate` is incremented by an amount proportional to the fraction of the total ARTH supply that was redeemed
* The redemption rate is given by `min{REDEMPTION_FEE_FLOOR + baseRate * ETHdrawn, DECIMAL_PRECISION}`

Upon each debt issuance:

* `baseRate` is decayed based on time passed since the last fee event
* The borrowing rate is given by `min{BORROWING_FEE_FLOOR + baseRate * newDebtIssued, MAX_BORROWING_FEE}`

`REDEMPTION_FEE_FLOOR` and `BORROWING_FEE_FLOOR` are both set to 0.5%, while `MAX_BORROWING_FEE` is `1%` and `DECIMAL_PRECISION` is `100%`. These values can be changed at any time via [Governance](../what-is-maha.md).

### Intuition behind fees

The larger the redemption volume, the greater the fee percentage. The longer the time delay since the last operation, the more the `baseRate` decreases.

The intent is to throttle large redemptions with higher fees, and to throttle borrowing directly after large redemption volumes. The `baseRate` decay over time ensures that the fee for both borrowers and redeemers will “cool down”, while redemptions volumes are low.

Furthermore, the fees cannot become smaller than `0.5%`, which in the case of redemptions protects the redemption facility from being front-run by arbitrageurs that are faster than the price feed. The 5% maximum on the issuance is meant to keep the system (somewhat) attractive for new borrowers even in phases where the monetary is contracting due to redemptions.
