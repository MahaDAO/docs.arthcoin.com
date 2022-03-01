# Recovery Mode

Recovery Mode is triggered when the Total Collateral Ratio or TCR of the system drops below 150%.

Minimum Collateralization Ratio in **Normal mode**: 110%\
Minimum Collateralization Ratio in **Recovery mode**: 150%

New loans can only be taken out if the borrower sets a CR% of >=150%.

{% hint style="warning" %}
During Recovery Mode, loans with a collateral ratio **below 150%** can be liquidated.&#x20;
{% endhint %}

'Recovery Mode' is initiated to make sure new borrowers take out loans that do not further reduce the TCR, and help raise the TCR back above 150%. Furthermore, it's also an incentive for ARTH holders to participate in the Stability Pool and provide more ARTH to the pool.\
\
As a system design, Recovery Mode is best avoided. Thus, the possibility of going into recovery mode should be a crucial point for ecosystem participants to make amends to their position, to ensure that they do not go into Recovery Mode.

## FAQs

### **What is the collateralization ratio in Recovery Mode?**&#x20;

The CR in Recovery Mode is 150%. While the CR in normal mode is 110%.&#x20;

### **Do fees change during Recovery Mode?**

Yes. While the redemption fee remains the same, the borrowing fee is set to 0% to encourage borrowing in the system.&#x20;

### **Measures to remain safe in Recovery Mode?**

As a borrower, simply increasing your collateral ratio to >150% will protect you from any liquidations. Thus, you will have to either&#x20;

* Add more collateral or&#x20;
* Repay some debt&#x20;

### Can I be liquidated if my collateral ratio is below 150% in Recovery Mode?&#x20;

Yes. During recovery mode your position can be liquidated if it falls below 150% CR. Otherwise, during normal circumstances, the CR will remain at 110%. It is advised to both monitor and adjust as needed to avoid liquidation risk.
