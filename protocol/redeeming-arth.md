# Redeeming ARTH

When ARTH is redeemed, the collateral provided to the redeemer is allocated from the Loans(s) with the lowest collateral ratio (even if it is above `110%`). If at the time of redemption you have the loan with the lowest ratio, you will give up some of your collateral, but your debt will be reduced accordingly. &#x20;

The $GMU value by which your collateral is reduced corresponds to the nominal ARTH amount by which your Loan's debt is decreased. You can think of redemptions as if somebody else is repaying your debt and retrieving an equivalent amount of your collateral. As a positive side effect, redemptions improve the collateral ratio of the affected Loans, making them less risky.

Redemptions that do not reduce your debt to 0 are called partial redemptions, while redemptions that fully pay off a Loan's debt are called full redemptions. In such a case, your loan is closed, and you can claim your collateral surplus and the Liquidation Reserve at any time.&#x20;

Let’s say you have a loan with `200 MAHA` collateralized and a debt of `3,200 ARTH`. The current price of MAHA is `20 $GMU`. This puts your collateral ratio (CR) at `125% (= 100% * (20 * 200) / 3,200)`. Let’s imagine this is the lowest CR in the protocol and look at two examples of a partial redemption and a full redemption:

**Example of a partial redemption**

Somebody redeems `1,200 ARTH` for `60 MAHA` and thus repays `1,200 ARTH` of your debt, reducing it from `3,200 ARTH` to `2,000 ARTH`. In return, `60 MAHA,` worth `1,200 $GMU`, is transferred from your loan to the redeemer. Your collateral goes down from `200 MAHA to 140 MAHA`, while your collateral ratio goes up from `125%` to `140% (= 100% * (20 * 140) / 2,000)`.

**Example of a full redemption**

Somebody redeems `6,000 ARTH` for `300 MAHA`. Given that the redeemed amount is larger than your debt minus  `5 ARTH` (set aside as a Liquidation Reserve), your debt of `3,200 ARTH` is entirely cleared and your collateral gets reduced by `3,195 $GMU` of MAHA, leaving you with a collateral of `40 MAHA (= 200 - 3,200 / 20)`.
