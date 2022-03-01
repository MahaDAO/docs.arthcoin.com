# Redeeming ARTH

When ARTH is redeemed, the collateral provided to the redeemer is allocated from loans with the lowest collateral ratio even if it is above the minimum collateral ratio `110%`.&#x20;

During a redemption, the borrower who has a loan with the lowest ratio will have to give up some of their collateral to the redeemer, but in return, their ARTH debt will be reduced accordingly. .&#x20;

{% hint style="info" %}
During a redemption, the value by which your collateral is reduced corresponds to the nominal ARTH amount by which your loan's debt is decreased.&#x20;
{% endhint %}

Redemptions can be thought of as somebody else repaying your debt and retrieving an equivalent amount of your collateral. As a positive side effect, redemptions help improve the collateral ratio of the affected loans, making them less risky.&#x20;

There are two kinds of redemptions:

* Partial Redemptions where your debt is partially reduced (not to 0).
* Full Redemptions where your debt is fully reduced to 0.

### Partial Redemptions

In such a case, your loan is closed, and you can claim your collateral surplus and the Liquidation Reserve at any time.&#x20;

Let’s say you have a loan with `200 MAHA` collateralized with a debt of `3,200 ARTH` and the current price of MAHA is `20 $GMU`.

This puts your collateral ratio (CR) at `125%` `(= 100% * (20 * 200) / 3,200)`. Let’s imagine this is the lowest CR in the protocol and look at two examples of a partial redemption and a full redemption:

**Example of a partial redemption**

Somebody redeems `1,200 ARTH` for `60 MAHA` and thus repays `1,200 ARTH` of your debt, reducing it from `3,200 ARTH` to `2,000 ARTH`.&#x20;

In return, `60 MAHA,` worth `1,200 $GMU`, is transferred from your loan to the redeemer. Your collateral goes down from `200 MAHA to 140 MAHA`, while your collateral ratio goes up from `125%` to `140% (= 100% * (20 * 140) / 2,000)`.

**Example of a full redemption**

Somebody redeems `6,000 ARTH` for `300 MAHA`. Given that the redeemed amount is larger than your debt minus  `5 ARTH` (set aside as a Liquidation Reserve), your debt of `3,200 ARTH` is entirely cleared and your collateral gets reduced by `3,195 $GMU` of MAHA, leaving you with a collateral of `40 MAHA (= 200 - 3,200 / 20)`.

In both cases, the net value of your position minus the debt remains the same, however during a redemption your exposure to the underlying asset decreases.&#x20;

## Redemption Fees

Under normal operation, the redemption fee is given by the formula `(baseRate + 0.5%) * collateral redeemed`

### How is the `baseRate` calculated?

Redemption fees are based on the `baseRate` state variable, which is dynamically updated. The `baseRate` increases with each redemption, and decays according to time passed since the last fee event - i.e. the last redemption or issuance of ARTH.

Upon each redemption:

* `baseRate` is decayed based on time passed since the last fee event
* `baseRate` is incremented by an amount proportional to the fraction of the total ARTH supply that was redeemed
* The redemption fee is given by `(baseRate  + 0.5%) * ETHdrawn`

## Stability Fees

For every redemption, the ARTH holder will have to pay a fee which is a percentage of the value being liquidated in MAHA tokens.

This acts as a method to dampen the redemption of bonds which can often create a negative price impact if done all too quickly. The stability fee is not meant to de-incentivize ARTH holders from redeeming their bonds but rather used to control the speed at which they do so.

The stability fee is managed via [Governance](governance.md).

## FAQs

### Is redemption the same as paying back my debt?&#x20;

No, redemptions are a completely separate mechanism. All one has to do to pay back their debt is adjust their loan's debt and collateral.&#x20;

### As a borrower, do I lose money if I'm redeemed against?&#x20;

If your loan is redeemed against, you _do not_ incur a net loss. However, you will lose some of your ETH exposure. Your loan's collateral ratio will also improve after a redemption.&#x20;

### How can I avoid my loan's collateral being redeemed?&#x20;

The best way to avoid being redeemed against is by maintaining a high collateral ratio relative to the rest of the loans in the system. The riskiest loans (i.e. lowest collateralized loans) are first in line when a redemption takes place.&#x20;
