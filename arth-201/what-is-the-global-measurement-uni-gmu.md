---
description: This page talks about the target price of ARTH and defines the GMU index
---

# Target price of ARTH

Because stablecoins are almost always pegged to a target price, it is ideal for them to revolve around that price. Most stablecoins are pegged to the $1 price or another fiat currency \(like Japanese Yen, Chinese Yuan, etc\). 

ARTH, however, is price pegged to the Global Measurement Unit \(GMU\). For simplicity purposes, ARTH's initial target price is set at $1.  
  
As the pegged price is used as an anchor, if the current value of the ARTH falls on either side of the target price, the protocol either re-collateralizes or performs buybacks to meet the target price.

Most stablecoin provide nothing more than just a USD stablecoin that competes with the utility of existing stablecoins like USDT, USDC, DAI, etc.

## What is the Global Measurement Unit \(GMU\)?

ARTH uses a special method of measuring an asset’s buying power called the Global Measurement Unit \(GMU\) which represents a basket of assets carefully selected with adequate weights to present a strong hedge strategy against economic turbulence and risks such as inflation and currency risk. 

As a result, the target price of ARTH is not going to be fixed to 1 US Dollar, but rather, the combined value of the assets which form part of the basket.

The basket consists of several assets, some of which are traditional, well-known financial assets and others are new age, digital financial assets. Precisely speaking, the GMU consists of the following assets and their respective weights:

* **80% — Collection of Fiat currencies** \(this includes USD, GBP, INR, JPY, CNY, CHF, CAD\)
* **15% — Gold \(**often considered a safe-haven asset
* **5% — Bitcoin \(**also started to show properties of being a safe have asset as of recently\)

Based on prior research we believe that these 3 assets, when combined in the right way, can provide a safe and sound base for preventing ARTH from depreciating in value.

## How were the weightings of the GMU calculated?

A methodological process was followed in order to determine the weightings of each portion of the GMU, specifically, extensive analysis was conducted across globally available metrics and data from prominent financial institutions such as the IMF in order to determine the average percentage makeup of these assets across both economies and portfolios globally.

A detailed excel sheet with weighting calculations is made public over here: [**https://docs.google.com/spreadsheets/d/1Um6qI8kKPwOj3wiw\_8ZVdRtgYhmI0lZLBXjRN2canWs/edit?usp=sharing**](https://docs.google.com/spreadsheets/d/1Um6qI8kKPwOj3wiw_8ZVdRtgYhmI0lZLBXjRN2canWs/edit?usp=sharing)\*\*\*\*

### **A. Calculating the Currency weighting**

The countries and their currencies were analyzed on the basis of their average share of world real GDP \(measured in constant 2010 US$\) between the years 2011 and 2019, with a minimum requirement of at least 2% of a share in world GDP.

Currencies included in **the** basket come from countries that accounted for more than 70% of the world Base GDP. At this moment countries which fulfill mentioned conditions were as per the following table:

![](../.gitbook/assets/image%20%286%29.png)

In addition to this well-known IMF basket of currencies, we also chose currencies such as the Swiss franc, Indian rupee, Brazilian real, and Canadian dollar so that the basket can act as a better diversifier. 

The Swiss franc is the only currency from the basket whose country doesn’t meet the requirement of 2% in World GDP share however we made an exception due to the fact that the Swiss franc and Japanese yen are generally looked upon from investors' point of view as a safe heaven. These 2 currencies have proven to be investors' favorite choice during crises.

### **B. Calculating the Gold weighting**

Throughout history, gold has been proven to be the most trusted asset in difficult times hence gold has found itself a place in the global measurement unit. 

The decision to include gold was not based merely on the presumption that gold has been viewed upon as a store of value but on the fact that central banks still hold gold as foreign exchange reserves. 

Keeping significant amounts of gold in foreign exchange reserves is a part of a more conservative  Central bank’s strategy, regarding gold’s hedge capability, against risky assets, gold is considered as a safe haven.  

After analyzing major central banks' foreign exchange reserves, the conclusion was that gold should be weighted with a weight of not less than 15%. 

When specific events occur, such as a surge in the price of BTC, the weighting of gold should increase, and the weighting of BTC should decrease, and vice versa, in order to prevent drastic volatility of the GMU's value.

### **C. Calculating the BTC weighting**

Bitcoin has been chosen because its price reflects spillovers from all other financial and commodity markets. 

Research has shown that Bitcoin and Gold provide a strong hedge against inflation. Based on research, followed by a conservative portfolio diversification strategy which suggests a ratio of risk-free v/s risky \(ratio of gold and bitcoin\) asset to be 3:1, Bitcoin should be weighted with a weight of 5%.

## **Final GMU calculation**

$$
GMU = (80 * Fiat + 15 * Gold + 5 * Bitcoin) / 100
$$



