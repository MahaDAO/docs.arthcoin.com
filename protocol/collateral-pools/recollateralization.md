---
description: >-
  This page explains what is recollateralization and how it effects the
  protocol.
---

# Recollateralization

If the protocol finds that one of its collateral pools does not have enough collateral to meet the collateralization ratio \(CR\), the protocol opens up the pool for re-collateralization. 

Recollateralization allows users to deposit collateral into the pool and in turn receive a discount in ARTHX proportionate to how much collateral they've deposited.

## Bonding curve discounts

The discount a user receives by re-collateralizing the protocol is based on a bonding curve which gives more rewards to people who participate in re-collateralizing the protocol early on.

If the protocol starts at a 10% collateralization ratio \(CR\) and has a target of 80% collateralization ratio, then the protocol calculates the distance from the target CR ratio, using this formula

$$
x = \dfrac{CR_{target} - CR_{current}}{ CR_{target} }
$$

Once the distance is calculated, it is applied to a bonding curve with the following parameters.

$$
Discount = \dfrac{10 ^ x - 1}{10}  * Discount_{max}
$$

This implies that early participants who re-collateralize the protocol will earn a higher discount in ARTHX than those who re-collateralize the protocol later.

