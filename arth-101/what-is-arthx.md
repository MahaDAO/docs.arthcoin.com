---
description: This page talks about the ARTHX stability token.
---

# What is ARTHX?

ARTH Shares \(ARTHX\) is the solution in bringing stability to ARTH and allow the ARTH ecosystem to scale efficiently. The ARTHX token is a deflationary token designed to absorb the volatility of the ARTH token and keeping the ARTH token stable.

It follows a similar model of fractional reserve stablecoins such as Frax protocol, with one main key differentiator, which is that the protocol is over-collateralized (110%) rather than under-collateralized.

When ARTH is trading above its peg (initially at 1$), arbitrageurs will mint ARTH by providing collateral and sell ARTHX in the open market to realize a profit. Hence bringing the price of ARTH down to the 1$ mark.

When ARTH is trading below its peg (initially at 1$), arbitrageurs will redeem ARTH along with ARTHX from the open market to get back the underlying collateral to realize a profit. Hence reducing the supply of ARTH to meet the actual demand for it.

![](../.gitbook/assets/arth-v2.0-2-.png)

## Deflationary Pressure for the ARTHX token

ARTHX besides having a utility within the ARTH ecosystem is also designed to be a deflationary token.
This means that when a user transacts with ARTHX by sending it from one wallet to another, a transaction fee is charged which is then redirected towards the staking pools or burnt off from the supply.
Hence, users who hold ARTHX and stake in any of the staking pools will be rewarded by the deflationary transaction fee encouraging long term holding of the ARTHX token.

## How will ARTHX be minted or burnt?

ARTHX is minted when a user decides to deposit collateral into the protocol to mint ARTH tokens. Because the platform is over collateralized it will mint ARTHX tokens proportional to the value of the collateral that was put in, in a 1:9 ratio.

This means that if a user deposits 100$ worth of collateral, he will mint 90$ worth of ARTH and 10$ worth of ARTHX. This is how the protocol ensures that every ARTH is backed by at least 110% more collateral.

ARTHX is burned when a user decides to withdraw collateral from the protocol by burning ARTH tokens. Similar to the case above, ARTHX is burnt proportional to the value of the collateral that has been redeemed, in a 1:9 ratio.

This means if a user wants to withdraw 100$ worth of collateral, he needs to supply 90$ worth of ARTH and 10$ worth of ARTHX.

## Supply of ARTHX

There is no max supply for the ARTHX token, it can increase/decrease depending on how the market moves.

If users decide to mint new ARTH tokens, then more ARTHX tokens are minted, thereby increasing the supply. Likewise, if users decide to redeem ARTH tokens, then ARTHX tokens are burnt, thereby decreasing the supply.

## How will ARTHX respond in a crypto market?
In a crypto market (which at the moment is primarily dominated by Bitcoin), there are three possible states the market can be; Bullish, bearish, or sideways. In each of these scenarios, we examine how ARTHX would behave.

**In a bull market,** there will be users who would like to sell ARTH to get into volatile assets such as Bitcoin/Ethereum. In this scenario, we could possibly see ARTH fall below its peg as users keep selling ARTH. In this scenario, arbitrageurs would buy ARTHX and redeem ARTH for its underlying collateral. This means a bull market is good for ARTHX but bad for ARTH.

**In a bear market,** users will be cashing out their volatile assets into stablecoins such as USDT/ARTH. In this scenario, there will be more buy demand for ARTH, and because of which we could possibly see ARTH go above its peg. In this scenario, arbitrageurs would deposit collateral to mint new ARTH tokens and receive a portion of ARTHX tokens which they’ll sell-off in the market. This means a bear market is bad for ARTHX but good for ARTH.

## What are the common risks with ARTHX?

While there are many potential benefits in holding ARTHX, there are also risks that come along with the benefits. The risks have been outlined below.

**Oracles/Flash loan attacks:** All oracles use a 1hr TWAP Uniswap oracle and are secured using multi-sig ownership. Later on, we will be migrating the oracles to use Chainlink oracles.

**A Bank run or Soros attack:** Most fractional reserve coins such as Frax, Pegs cash, Titan, TerraLuna are all susceptible to Bank Run attacks because of their under-collateralized nature. Furthermore, these protocols are also more susceptible to a Soros attack. ARTH/ARTHX however mitigates this by making sure that the protocol at every point in time is over-collateralized rather than under-collateralized. This makes the cost of conducting a bank run or organizing a Soros attack relatively expensive.

**Under-collateralization Risk:** In the event that the protocol’s underlying collateral does not become enough to give enough backing to the ARTH stablecoin (that is net collateral in the system drops below ~100%); then the system will grind to a halt and pause the mint/redeem functions only allow users to redeem their ARTH for their underlying collateral at a fixed price of ARTHX.

**Smart-contract or Economic Exploits:** Given the fact that the ARTH/ARTHX protocol is relatively new technically and economically, there could be the possibility of exploits still occurring which haven’t yet been foreseen by the general public or audit firms.
