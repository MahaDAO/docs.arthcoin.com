---
description: >-
  When using the protocol please make sure you are aware of all the various
  risks involved in using the protocol. In this section, we explain the various
  risks involved when interacting with the ARTH an
---

# Risks & Security

### Bug Bounty

The MahaDAO offers a bug bounty program for responsible bug disclosures.

We are limiting the scope of the program to critical and high-severity bugs in the core contracts and are offering a reward of up to 10,000 `MAHA`. Happy hunting!

### Audits

MahaDAO smart contracts are a fork of Liquidity that has been audited by [Trail of Bits](https://github.com/trailofbits/publications/blob/master/reviews/Liquity.pdf).

However, security audits don't eliminate risks completely. So please don’t supply your life savings or assets you can’t afford to lose to the protocol, especially as a liquidity provider.

The MahaDAO will continue to run regular and ongoing audits funded by the community's treasury.

### Risk of Liquidations

In the event of a market black swan or if the price of collateral drops significantly, then all loans that fall below the minimum collateral ratio (110% in most cases get liquidated), this is a loss to all borrowers.

Furthermore, if the total collateral ratio of particular collateral falls below the recovery mode collateral ratio (150% in most cases), then all loans that are also below the minimum collateral ratio also become eligible for liquidations.

To learn more about liquation, read about it [here](liquidations.md).&#x20;

We recommend borrowers always keep a high collateral ratio to avoid getting liquidated.

### Risk of Redemption

In the event of a redemption, loans with the lowest collateral ratio lose their exposure to the underlying collateral.

To learn more about how redemptions affect your loan, read about it [here](redemptions.md#as-a-borrower-do-i-lose-money-if-im-redeemed-against).

We recommend borrowers always keep a higher collateral ratio than other loans to avoid getting redeemed.

### Oracle Risks

The protocol uses price oracles that inform the protocol on the collateral ratio of various loans. An attack on oracles can cause the attacker to manipulate the price feed and hence cause unwanted liquidations.

To mitigate oracle risks, the `ARTH` protocol uses chainlink and umbrella finance oracles for the various collaterals.

### Collateral Risk

In the case of a black swan event where one of the collateral loses its underlying value, all loans backing the underlying collateral will suddenly get liquidated, causing all borrowers who have borrowed `ARTH` using the affected collateral to get liquidated.

This type of event could also cause temporary harm to the `ARTH`'s peg.

To mitigate collateral risk, `ARTH`'s collateral exposure is diversified so that there is no heavy risk from a single type of collateral.

Furthermore, rigorous checks and balances are put in place before new collateral is onboarded.

### Bridge Attacks

`ARTH` is only minted/burnt on the Ethereum blockchain. Deployment on various other sidechains (or layer 2 chains) exist as simply bridged tokens that were originally issued on the Ethereum chain.&#x20;

In the case of a hack on any of the bridges supporting these bridged tokens, the backing of these bridged token is lost, reducing its underlying value and can a loss to holders on the bridged chain.

eg: [https://arstechnica.com/information-technology/2022/02/how-323-million-in-crypto-was-stolen-from-a-blockchain-bridge-called-wormhole/](https://arstechnica.com/information-technology/2022/02/how-323-million-in-crypto-was-stolen-from-a-blockchain-bridge-called-wormhole/)
