# Algorithmic or Elastic stablecoins

With algorithmic stablecoins, the currency's supply algorithmically expands and contracts based on demand for the coin.

![](../.gitbook/assets/image%20%2836%29.png)

The first of this type of stablecoin to gain widespread attention was Ampleforth's AMPL token via it's "rebasing" mechanism. As demand for the AMPL rises, it's price increases, and the supply automatically increases until the price reverts back to its peg. And vice versa, as demand for the AMPL falls, reducing price, the supply automatically contracts until the price reverts back to its peg. This process happens every 24 hours via the smart contract based on the 24 hour volume weighted average price from price oracles \(currently ChainLink\).

![](../.gitbook/assets/image%20%2870%29.png)

As an output, the Ampleforth protocol seeks to reflect demand changes in quantity rather than price.

The Ampleforth paper describes this process using the following example:

Imagine Alice purchases 1 Ample for $1  
Demand suddenly increases, and she now has 1 Ample worth $2

In the case above, the system will seek a price-supply equilibrium, such that Alice ends up with 2 Amples each worth $1. And the opposite is true when demand decreases. Continuing from the example above:

Alice has 2 Amples each worth $1  
Demand suddenly decreases, and she now has 2 Amples each worth $0.50

Now you may be asking, why bother? Whether Alice holds 1 Ample worth $2, or 2 Amples each worth $1, makes no difference in terms of net balance since \(1 x $2\) = \(2 x $1\). But there are two key benefits to seeking price-supply equilibrium:

1. It applies countercyclical pressures
2. It encourages a stable unit price

Ampleforth is different to most supply designs in that it doesn't rely on seignorage or reserve assets to contract supply \(buy the stable coin with other assets\), in comparison the rebase function immediately multiplies/divides existing tokens by some value dependent on the price divergence.

_Source:_ [_https://www.ampleforth.org/redbook/_](https://www.ampleforth.org/redbook/)\_\_

