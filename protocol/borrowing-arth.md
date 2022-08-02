---
description: >-
  As the primary use case of the loans platform, let's see how borrowing works
  and how you can benefit with it.
---

# Collateral Ratios

ARTH is a borrowing protocol for users looking to leverage on `ETH`.

Users can lock up their `ETH` & borrow `ARTH` against the collateral. Redeeming a loan position can be done quite easily. You can get your assets back once you repay your position in ARTH valuecoin.

For borrowing; a user has to open a loan position & deposit a certain amount of collateral for it. A user can then, draw ARTH depending upon the collateral ratio they have set. Users can set a collateral ratio of anything up to `110%` and above.

{% hint style="info" %}
### Collateralization Ratio (CR)
{% endhint %}

Let's understand the collateralization ratio in further detail.

The CR or collateralization ratio is the ratio that determines how much ARTH a borrower will receive for the assets he is willing to collateralize.\
\
The CR is set by the user. The minimum CR required is 110%.

**Example 1:** If user A sets a CR of `110%` and creates a position of `10,000$` in `ARTH`, he would have to at least collateralize `11,000$` worth of `ETH`. This position is highly prone to liquidation, if the CR% falls below `110%`.

**Example 2:** If user B sets a CR of `150%` and creates a position of `10,000$` in `ARTH`, he would have to at least collateralize `15,000$` worth of `ETH`. This position is more secure than Example 1.

A higher CR% means a user's position is less prone to [liquidation](liquidations.md). but also means that he/she will receive less `ARTH` for the collateralized position. Whereas a lower CR% means the user's position is more prone to liquidation, he will receive more `ARTH` for his/her collateralized position.

### Minimum Collateralization Ratio (MCR)

The `Minimum Collateralization Ratio (or MCR)` is the lowest ratio of collateral that will not trigger a liquidation. This is set at 110% under normal conditions.

Whereas in [**recovery mode**](recovery-mode.md)**,** this MCR is set to 150%. To avoid liquidation during Recovery Mode, it is recommended to keep the ratio above 150%.

{% hint style="info" %}
As a borrower, you should make sure you open a loan with a high enough collateral ratio (we recommend 200%+) to avoid getting liquidated and suffer a loss of funds.
{% endhint %}
