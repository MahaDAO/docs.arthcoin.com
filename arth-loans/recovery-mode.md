# Recovery Mode

Recovery Mode is triggered when the [T](https://docs.liquity.org/faq/recovery-mode#what-is-the-total-collateralization-ratio)otal Collateral Ratio or TCR of the system falls below 150%. 

During Recovery Mode, loan positions with a collateral ratio **below the TCR** \(i.e. in the worst case up to 150%\) can be liquidated. 

Moreover, the system blocks borrower transactions that would further decrease the TCR. New LUSD may only be issued by adjusting existing Troves in a way that improves their collateral ratio, or by opening a new Trove with a collateral ratio`>=150%`. In general, if an existing Trove's adjustment reduces its collateral ratio, the transaction is only executed if the resulting TCR is above `150%`. 

The goal of Recovery Mode is to incentivize borrowers to behave in ways that promptly raise the TCR back above 150%, and to incentivize LUSD holders to replenish the Stability Pool.

Economically, Recovery Mode is designed to encourage collateral top-ups and debt repayments, and also itself acts as a self-negating deterrent: the possibility of it occurring actually guides the system away from ever reaching it. Recovery Mode is not a desirable state for the system. 

