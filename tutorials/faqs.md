# FAQs

### How can I earn money with ARTH Loans?

Although the primary use case of `ARTH` Loans is not generating revenue, instead, it is for users to take out seamless loans in a stable valuecoin, that is resistant to inflation. DeFi users, however, can generate revenue via:

* Liquidating low CR% loans
* Depositing `ARTH` valuecoin to the [Stability Pool](../protocol/stability-pool.md) to earn liquidation rewards. Stability Pools always give net positive rewards over time
* Participate in various staking/LP pools with partner projects and earn rewards in `MAHA` and partner tokens

### Pre-requisites for taking out a loan?

* Metamask or any web3 compatible wallet installed.
* Collaterals in the form of the native blockchain token (`ETH`).

### Pre-requisites for becoming a Stability Provider?

To become a Stability Provider, you need `ARTH`.

`ARTH` can be borrowed by putting in collateral in the form of opening a loan position. Alternatively, you can also buy `ARTH` from the open market directly from a DEX.

### What is the gas fee compensation?

To make liquidations profitable, the borrower needs to keep away a gas fee compensation at the time of borrowing `ARTH`. The current gas fee compensation is 5 `ARTH` (or roughly $10) on PoS chains and roughly 50 `ARTH` on the `ETH` chain

### What is the minimum requirement to create a loan position?

A borrower can only take out a loan, by creating a debt position of not less than 50 `ARTH` on PoS chains and 250 `ARTH` on the `ETH` chain.

### Who can liquidate a loan position?&#x20;

Almost anybody can liquidate a loan position.&#x20;

The requirement to liquidate a loan position is simply:&#x20;

`Current Collateralization Ratio < Minimum Collateralization Ratio`&#x20;

Minimum Collateralization Ratio in **Normal mode**: 110% \
Minimum Collateralization Ratio in **Recovery mode**: 150%&#x20;

For every liquidation, the liquidator will have to pay gas fees. To make sure, liquidations are profitable, a significant gas fee is kept aside at the time of borrowing a loan.&#x20;

Currently, the gas fee compensation is set at 5 ARTH or $10 acc to the current GMU of $2.&#x20;

### **What is the collateralization ratio in Recovery Mode?**&#x20;

The CR in Recovery Mode is 150%. While the CR in normal mode is 110%.&#x20;

Yes. While the redemption fee remains the same, the borrowing fee is changed to 0% to encourage borrowing in the system.

As a borrower, simply increasing your collateral ratio to >150% will protect you from any liquidations. Thus, you will have to either a) add more collateral or b) repay some debt&#x20;

### Can I be liquidated if my collateral ratio is below 150% in Recovery Mode?&#x20;

Yes. You will be in line for liquidations if the loans who have a collateral ratio below yours aren't enough to bring the protocol back out of recovery mode.

## Any Further Questions?

If you have any further questions, you'd like us to answer

* You can join our discord channel [https://discord.gg/mahadao](https://discord.gg/mahadao) and ask the discord community for help.
* You can join our main telegram chat [https://t.me/mahadao](https://t.me/mahadao) and ask the telegram community for help. Telegram is for quick and short queries.
* If you have a long and complicated query, you can create a thread on [https://discuss.mahadao.com/](https://discuss.mahadao.com)
