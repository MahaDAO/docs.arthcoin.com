# Tying ARTHB to MahaSwap

One of the biggest differentiators in the ARTH protocol is the fact that purchasing ARTH bonds have a strong impact on the price of the ARTH-DAI MahaSwap pool.

![](../../.gitbook/assets/image%20%287%29.png)

In current implementations of Seignorage-based coins, bonds tokens \(or coupons\) are purchased by burning the stablecoin whenever the protocol is in its contraction phase.

However, contracting the supply has a very weak effect on the price of the stablecoin especially if the demand is mostly coming from speculators. The only way for the protocol to come out of this cycle is to contract the supply to such an extent where it’ll finally meet the demand from genuine buyers and this process can result in high periods of volatility.

This then causes the protocol to also have longer contraction cycles and start to accumulate more and more debt which can slowly become very dangerous in the long-term.

To counter this, the ARTH protocol improves upon the idea of bond tokens, by tying the purchase of bond tokens to the MahaSwap price of the stablecoin.

This means, that whenever a buyer purchases ARTH Bonds, DAI used to buy ARTHB is sent to MahaSwap to purchase ARTH. ARTH that is bought back is then burnt and in return, ARTHB \(ARTH Bond\) is minted and sent back to the buyer.

![A screenshot of the ARTH Bonds purchase page](../../.gitbook/assets/image%20%2860%29.png)

By doing this, the purchasing of ARTH bonds has two direct impacts on the price of ARTH:

* Appreciation of ARTH \(by selling DAI on the ARTH-DAI MahaSwap pool\)
* Reduction of ARTH supply \(as ARTH is burnt for ARTHB\)

