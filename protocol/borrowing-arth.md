---
description: >-
  As the primary use case of the loans platform, let's see how borrowing works
  and how you can benefit with it.
---

# Collateral Ratios

Users can lock up their `ETH` & borrow `ARTH` against the collateral. Redeeming a loan position can be done quite easily. You can get your assets back once you repay your position in `ARTH` valuecoin.

For borrowing, a user has to open a loan position & deposit a certain amount of collateral for it. A user can then draw `ARTH` depending upon the collateral ratio they have set. Users can set a collateral ratio of anything up to `110%` and above.

There are four kinds of collateral ratios to consider.

### Individual Collateralization Ratio (ICR)

The ICR or Individual collateralization ratio is the ratio that determines how much `ARTH` a borrower will receive for the `ETH` they are willing to collateralize.\
\
The CR is set by the user when a loan is opened and can be adjusted later on by adding/removing collateral or debt. The minimum CR required is `110%`.

**Example 1:** If user A sets a CR of `110%` and creates a position of `10,000$` in `ARTH`, they would have to at least collateralize `11,000$` worth of `ETH`. This position is highly prone to liquidation if the CR% falls below `110%`.

**Example 2:** If user B sets a CR of `150%` and creates a position of `10,000$` in `ARTH`, they would have to at least collateralize `15,000$` worth of `ETH`. This position is more secure than Example 1.

A higher CR% means a user's position is less prone to [liquidation](liquidations.md). But, it also means that they will receive less `ARTH` for the collateralized position. Whereas a lower CR% means the user's position is more prone to liquidation, and they will receive more `ARTH` for their collateralized position.

### Minimum Collateralization Ratio (MCR)

The `Minimum Collateralization Ratio (or MCR)` is the lowest ratio of collateral that will not trigger a liquidation. This is set at 110% under normal conditions.

Whereas in [**recovery mode**](recovery-mode.md)**,** this MCR is set to 150%. To avoid liquidation during Recovery Mode, it is recommended to keep the ratio above 150%.

{% hint style="info" %}
As a borrower, you should make sure you open a loan with a high enough collateral ratio (we recommend 200%+) to avoid getting liquidated and suffering a loss of funds.
{% endhint %}

### Total Collateral Ratio (TCR)

The `Total Collateral Ratio or TCR` is the ratio of the Dollar value of the entire system collateral at the current protocol price, to the entire system debt.&#x20;

In other words, it's the sum of the collateral of all loans expressed in the [protocol price](../target-price-for-arth.md), divided by the debt of all loans expressed in `ARTH`.

### Nominal Collateral Ratio (NCR)

A loan's nominal ICR is its entire collateral (in `ETH`) multiplied by `100e18` and divided by its entire debt.
