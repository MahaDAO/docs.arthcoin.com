---
description: This section explains about the rebase mechanism within the ARTH protocol.
---

# Rebase Mechanism

**A Rebase is a last resort mechanism** where the circulating supply of a token is adjusted so that it forces the current market price to meet the target price. The first rebase token that was introduced was Ampleforth.

Rebase tokens work by changing the balance of a user's wallet so that the amount in the user's wallet changes but the net value stays the same. 

For example, if the target price of ARTH is set as $1. And If its price goes above $1, the circulating supply expands during rebase, thereby reducing the value of each ARTH token. Conversely, if the price of ARTH dips below $1, the current supply contracts during rebase, thereby increasing the value of each token. From a user's point of view, the number of tokens increases or decreases as per the rebase mechanism. However, the net value of the token remains the same. 

To elaborate, if Alice has 1 ARTH, which doubles in value to become $2, the supply will inflate through the rebase mechanism. This means that Alice’s 1 ARTH will decrease to 0.5 ARTH, yet the value will still be $1 since 1 ARTH would now be worth $2.

## When are rebases triggered?

ARTH triggers a rebase when the value of the collateral locked cannot sustain the protocol's target price. Such an event could occur during the following scenarios:

1. During the ARTH Genesis Launch
2. A black-friday event

Rebases are triggered by Governance. 

_**The use of Rebase should be thought of only as a mechanism of last resort.**_

