# Liquidations

When a borrower's loan falls below the Minimum Collateralization Ratio of 110%, he/she is exposed to liquidation.

For example: 

* A borrower took out a loan of $10,000 by committing collateral in WETH with a CR% of 120%. 
* The borrower committed 4 WETH, taking WETH at a price of $3,000`($10,000*120%/3000)`
* For the loan position to be eligible for liquidation, the CR% needs to go below 110% 
* If the price of WETH fell by 10%\($2700\), his current CR% will fall to 108% \($2700\*4 WETH = $10,800 or 108% Collateralization Ratio\)
* **This loan position can then be liquidated by anybody**  

### Post Liquidation 

The debt of the loan position is fulfilled by the Stability Pool and its collateral is distributed among Stability Providers.

The borrower still keeps the loan amount he received in ARTH as part of the borrowed loan but loses approximately 10% in overall value for each liquidation + fees.    
  
**In the next section, learn how liquidations affect the Stability Pool rewards in favour of the Stability Pool providers.** 

