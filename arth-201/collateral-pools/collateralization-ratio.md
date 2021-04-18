---
description: >-
  This page explains what is the Collateralization ratio and how it influences
  the price.
---

# Collateralization Ratio

## What is the Collateralization Ratio \(CR\)?

The collateralization ratio is used by a collateral pool to determine how much of the pool is backed by actual collateral and how much of it is backed by ARTHX. 

Since ARTHX can be minted/burned as and when needed by a collateral pool, the CR determines the minimum amount of CR needed by a pool to maintain stability. 

At 0% CR, the collateral pool does not need to maintain any amount of collateral to allow for ARTH to be in circulation. To mint new ARTH tokens, users need to only deposit ARTHX and 100% worth of the ARTHX deposited is used to mint ARTH.

At 0-100% CR, the collateral pool requires X% of collateral and \(100 - X\)% of ARTHX to mint new ARTH tokens.

At 100% CR, the collateral pool requires collateral and no ARTHX tokens to mint new ARTH tokens.

## How does a change in CR affect the protocol?

A change in the CR is what makes ARTH a very capital efficient stablecoin. It allows ARTH to be undercollateralized but also remains stable as long as the ARTHX token has a strong position in the market.

A decrease in CR happens when the ARTH is going through a phase where there's a spike in demand. By reducing the CR, ARTH is become easier to be minted by ARTHX holders who now have a more significant share in the ARTH protocol.

Further, a decrease in CR could creates excess collateral which can be used by the protocol to buyback and burn ARTHX tokens. \(However, note that it is not encouraged to simply decrease the CR to trigger these buybacks. A very low CR could pose a risk to the stability of the protocol\).

An increase in CR happens when ARTH goes below the peg and the protocol realizes that it needs more collateral to support the peg. In such scenarios, the protocol triggers a re-collaterlize event, where it'll attempt to buy more collateral in exchange for newly minted ARTHX tokens. These newly minted ARTHX tokens can be sold off in the market to give a discount \(However note that this does create an unwanted sell pressure on the ARTHX token\). 

## Bootstrapping the CR

At the [launch](../../arth-101/arth-v2-phased-launch.md) of ARTH 2.0, the collateralization ratio will be set differently for redemption and for minting.

During the bootstrapping period, the redemption collateralization ratio will be set at 0% and the minting collateralization ratio will be set at 100%.

This means that during the bootstrapping phase, users that redeem their ARTH for the underlying collateral will get 0% collateral and 100% ARTHX for every ARTH they redeem.

Likewise, for users who would like to mint ARTH, they'll deposit 100% collateral and 0% ARTHX to mint ARTH proportionate to their collateral's worth.

This has the strong net effect of bootstrapping the collateralization ratio from 0% to a stable collateralization ratio.

