# FAQs

## General

### How can I earn money with ARTH Loans?

Although, the primary use case of ARTH Loans is not generating revenue, instead it is for users to take out seamless loans in a stable valuecoin, that is resistant to inflation. DeFi users, however, can generate revenue via: 

* Liquidating low CR% loans  
* Depositing ARTH valuecoin to the [Stability Pool](stability-pool.md) to earn liquidation rewards. Stability Pools always gives a net positive reward overtime.   
* Participate in various staking/LP pools with partner projects and earn rewards in MAHA and partner tokens. 

### Pre-requisites for taking out a loan?

* A metamask wallet 
* Collaterals in the form of WETH, WMATIC, DAI 

Please note: If you are familiar with only the ETH chain, you will have to bridge your tokens to Matic. This can be done simply with a few web searches. Here is the bridge link: [https://wallet.matic.network/bridge/](https://wallet.matic.network/bridge/)

### Pre-requisites for becoming a Stability Provider?

To become a Stability Provider, you need ARTH valuecoin. 

$ARTH can be borrowed by putting in collateral in the form of opening a loan position. Alternatively, you can also buy $ARTH from the open market directly from a DEX like [Dfyn](https://dfyn.network/).

### What is the gas fee compensation? 

To make liquidations profitable, the borrower needs to keep away a gas fee compensation at the time of borrowing ARTH. The current gas fee compensation is 5 ARTH or $10. This is significantly lower than the average gas fees on the ETH chain. Hence, Polygon Network.  

### What is the minimum requirement to create a loan position?  

A borrower can only take out a loan, by creating a debt position of not less than 500 ARTH or $1,000. 

## Stability Pool 

### Why should I become a Stability Pool Provider?

Stability Providers deposit ARTH into the stability pool, which acts as a supplement to the Loan platform. Depositing ARTH valuecoin to the [Stability Pool](stability-pool.md) earns you liquidation rewards.

Whenever a loan position is liquidated, the collateral used to fund the loan \(at 110%\), is returned to the Stability Pool.   
  
Stability Providers always remain in a safe and net positive position. 

### Can you give me a real-life example of how the Stability Providers benefit by funding the Stability Pool?

Liquidations happen below 110% Collateralization Ratio.  
  
Let's take a situation where: 

* Current ARTH Pooled in the stability pool: $1,000,000 or 500,000 ARTH \(1 $ARTH = 2 USD\) 
* You deposit $100,000 or 50,000 ARTH 
* Thus, you have a 10% stake in the Stability Pool
* A loan position of $200,000 gets liquidated at 109% collateral Ratio
* Collateral liquidated = Loan taken out \* CR% / Current Price of collateral `($200,000*109%/3000) =` **`72.66 WETH`**  

What do you pay: 

* Given that your pool share is 10%, your ARTH deposit will go down by 10% \(the ARTH you added into the Stability Pool is used to settle the debt into the system\) of the liquidated debt 
  * Total Debt to be settled = 200,000 USD
  * Your Debt Share = 10% 
  * Your Debt share = 20,000 USD \(10% of Total Debt\)
  * Your initial ARTH position: 100,000 USD
  * Your new ARTH position: **80,000 USD** \(Initial Position - Your Debt Share\) .

What do you get:

* In return, you will gain 10% of the liquidated collateral\(72.66 WETH\), i.e. **`7.26 WETH`**, which is currently worth $21,780\(Current WETH price: $3000\). Your net gain from the liquidation is `$1,780 USD`  

Note that depositors can immediately withdraw the collateral received from liquidations and sell it to reduce their exposure to a volatile asset like ETH, if the USD value of ETH is expected to decrease. 

## Liquidations 

### Who can liquidate a loan position? 

Almost anybody can liquidate a loan position. 

The requirement to liquidate a loan position is simply: 

`Current Collateralization Ratio < Minimum Collateralization Ratio` 

Minimum Collateralization Ratio in **Normal mode**: 110%   
Minimum Collateralization Ratio in **Recovery mode**: 150% 

### What do I get if I liquidate a loan position?

For every liquidation, the liquidator will have to pay gas fees. To make sure, liquidations are profitable, a significant gas fee is kept aside at the time of borrowing a loan. 

Currently, the gas fee compensation is set at 5 ARTH or $10 acc to the current GMU of $2. 

## Recovery Mode 

### **What is the collateralization ratio in Recovery Mode?** 

The CR in Recovery Mode is 150%. While the CR in normal mode is 110%. 

### **Do fees change during Recovery Mode?**

Yes. While the redemption fee remains the same, the borrowing fee is changed to 0% to encourage borrowing in the system. 

### **Measures to remain safe in Recovery Mode?**

As a borrower, simply increasing your collateral ratio to &gt;150% will protect you from any liquidations. Thus, you will have to either a\) add more collateral or b\) repay some debt 

### Can I be liquidated if my collateral ratio is below 150% in Recovery Mode? 

Yes - during recovery mode your position can be liquidated if it falls below 150% CR. Otherwise, during normal circumstances, the CR will remain at 110%. It is advised to both monitor and adjust as needed to avoid liquidation risk."   
  
---

If you have any further questions, you'd like us to answer

* You can join our discord channel [https://discord.gg/mahadao](https://discord.gg/mahadao) and ask the discord community for help.
* You can join our main telegram chat [https://t.me/mahadao](https://t.me/mahadao) and ask the telegram community for help. Telegram is for quick and short queries.
* If you have a long and complicated query, you can create a thread on [https://discuss.mahadao.com/](https://discuss.mahadao.com/) 





