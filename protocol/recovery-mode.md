# Recovery Mode

Recovery Mode is a special mode that is triggered when the [Total Collateral Ratio (TCR)](borrowing-arth.md#total-collateral-ratio-tcr) of the protocol drops below `150%`.

During Recovery Mode, liquidation conditions are relaxed, and the system blocks borrower transactions that would further decrease the TCR. New ARTH may only be issued by adjusting existing loans in a way that improves their [ICR](borrowing-arth.md#individual-collateral-ratio-icr), or by opening a new loan with an ICR of >=150%.&#x20;

In general, if an existing loan's adjustment reduces its ICR, the transaction is only executed if the resulting TCR is above 150%

{% hint style="warning" %}
If the protocol goes into recovery mode, then loans with a collateral ratio **below `150%`** can be liquidated until the protocol comes back out of recovery mode. In general, borrowers are encouraged to always maintain a collateral ratio above `150%`. \
\
To understand more about this behavior, read [recovery mode liquidations](liquidations.md#recovery-mode-liquidations).
{% endhint %}

**Recovery Mode** is initiated to make sure new borrowers take out loans that do not further reduce the TCR and help raise the TCR back above `150%`. Furthermore, it's also an incentive for `ARTH` holders to participate in the Stability Pool and provide more ARTH to the pool.\
\
As a system design, Recovery Mode is best avoided. Thus, the possibility of going into recovery mode should be a crucial point for ecosystem participants to make amends to their position, to ensure that they do not go into Recovery Mode.

## FAQs

### **What is the collateralization ratio in Recovery Mode?**&#x20;

The CR in Recovery Mode is 150%. While the CR in normal mode is 110%.&#x20;

### **Do fees change during Recovery Mode?**

Yes. While the redemption fee remains the same, the borrowing fee is set to 0% to encourage borrowing in the system.&#x20;

### **Measures to remain safe in Recovery Mode?**

As a borrower, simply increasing your collateral ratio to >150% will protect you from any liquidations. Thus, you will have to either&#x20;

* Add more collateral
* Repay some debt&#x20;

### Can I be liquidated if my collateral ratio is below 150% in Recovery Mode?&#x20;

Yes. During recovery mode, your position can be liquidated if it falls below 150% CR. Otherwise, during normal circumstances, the CR will remain at 110%. It is advised to both monitor and adjusts as needed to avoid liquidation risk.

### How much of a loan's collateral can be liquidated in Recovery Mode?

In Recovery Mode, liquidation loss is capped at `110%` of a loan's collateral. Any remainder, i.e. the collateral above `110%` (and below the TCR), can be reclaimed by the liquidated borrower using the standard web interface.

This means that a borrower will face the same liquidation “penalty” (`10%`) in Recovery Mode as in Normal Mode if their loan gets liquidated.
