---
description: This reviews the mechanics and scenarios that involve minting and burning ARTH
---

# Minting and Burning ARTH

ARTH has special mechanisms that allow it to be a highly scalable stablecoin. In this section, we explain the different scenarios where ARTH will be minted and burned.

![](../.gitbook/assets/image%20%281%29.png)

## When is ARTH minted?

ARTH is only minted when collateral is deposited into any one of the protocol pools. This ensures that every ARTH that is minted will always have some kind of backing to ensure its stability.

ARTH is never minted freely without some kind of collateral being deposited into the protocol.

Users will choose to mint ARTH when it is trading above its GMU peg. 

## When is ARTH burnt?

ARTH is burnt when it is redeemed for its underlying collateral. Since there are multiple pools, users can go to any one of the collateral pools to redeem their ARTH tokens.

ARTH is redeemed/burnt when ARTH is trading below its GMU peg.

## Special Case: Protocol Becomes Over Collateralized

Because ARTH is burnt more freely than it is minted, there could be a possibility where the protocol could become over collateralized due to the excessive burning of ARTH.

That is, the protocol could possibly contain more collateral than the current market cap of ARTH.  
  
When the protocol is overcollateralized, the protocol performs buyback and burn functions which uses the excess collateral to buy ARTHX from the market, thereby causing a decrease in supply and increase in demand for ARTHX. 

