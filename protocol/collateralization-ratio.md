---
description: >-
  This page explains the Collateralization Ratio is and how it influences the
  price.
---

# Collateralization Ratio

## What is the Collateralization Ratio (CR)?

The collateralization ratio is used by a collateral pool to determine how much of the pool is backed by actual collateral.&#x20;

At 0% CR, the collateral pool does not need to maintain any amount of collateral to allow for ARTH to be in circulation.&#x20;

## How does a change in CR affect the protocol?

A change in the CR is what makes ARTH a very capital efficient stable coin.

A decrease in CR happens when the ARTH is going through a phase where there's a spike in demand.&#x20;

An increase in CR happens when ARTH goes below the peg and the protocol recognizes that it needs more collateral to support the peg. In such scenarios, the protocol triggers a re-collaterlize event.&#x20;

## Bootstrapping the CR

At the [launch](broken-reference) of ARTH 2.0, the collateralization ratio will be set differently for redemption and for minting.

During the bootstrapping period, the redemption collateralization ratio will be set at 0% and the minting collateralization ratio will be set at 100%.

Likewise, for users who would like to mint ARTH, they'll deposit 100% collateral and 0% ARTHX to mint ARTH proportionate to their collateral's worth.

This has the strong net effect of bootstrapping the collateralization ratio from 0% to a stable collateralization ratio.
