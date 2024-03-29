---
description: This section talks about the ARTH peg
---

# What is ARTH Pegged to?

Because stablecoins are almost always pegged to a target price, it is ideal for them to revolve around that price. Most stablecoins are pegged to 1 USD  or another fiat currency (like Japanese Yen, Chinese Yuan, etc.).&#x20;

However, **ARTH** is fully pegged to ETH growth, which makes it highly liquid and resistant to central failures. For simplicity purposes, `ARTH`'s initial price was set at **2 USD worth of peg,** signifying the rise in inflation, among other things.

The goal of this peg is to achieve stability whilst at the same time slowly appreciating in value.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>ARTH price peg against ETH price. <a href="https://arth.loans/#/price">https://arth.loans/#/price</a></p></figcaption></figure>

In various simulations, it was found that the pegged value remained relatively stable in moments when the market turned bearish but started to appreciate ever so slightly whenever the market turned bullish.

{% hint style="info" %}
The ETH Oracle is currently deployed at[ 0x7ee5010cbd5e499b7d66a7cba2ec3bde5fca8e00](https://etherscan.io/address/0x7ee5010cbd5e499b7d66a7cba2ec3bde5fca8e00)
{% endhint %}

## How Does it Work?

The basic idea of Peg is to capture the appreciation of an underlying asset without causing too much volatility. In this case, the underlying asset is `ETH`.

To do this, it uses two moving averages. A 7-day moving average to understand the short-term price trend of the underlying asset (which is mainly used to understand when to stop the appreciation). And a 30-day moving average is used to understand the long-term price trend of an underlying asset (which is mainly used to understand how much to appreciate the price).

If both the 30-day and 7-day moving averages are in an upwards trend, then the indicator appreciates the peg by a fraction of the appreciation of the 30-day moving average.

{% code title="indicator.py" %}
```python
# https://github.com/MahaDAO/gmu-oracle-contracts/blob/master/simulation/indicator.py
def arth_indicator(pricesLongTerm, pricesShortTerm, startingPrice,  
  longTermDuration = 30, dampeningFactor = 0.1):
  '''
  An indicator to algorithmically calculate ARTH's price
  '''
  trend = [startingPrice] * longTermDuration

  # Ptn will help us attain the memory part of thresholds
  # assuming we start in the middle region
  for i in range(longTermDuration, len(pricesLongTerm)):
    # If we are going to change the price, check if both 
    # the 30d and 7d price are appreciating
    if (
      pricesLongTerm[i] > pricesLongTerm[i - 1] and 
      pricesShortTerm[i] > pricesShortTerm[i - 1]
    ):
      delta = pricesLongTerm[i] - pricesLongTerm[i - 1]
      percentageChange = delta / pricesLongTerm[i - 1]

      # dampen the change; say we will only appreciate ARTH by 10% 
      # of the bitcoin appreciation
      dampnedChange = percentageChange * dampeningFactor
      trend.append(trend[i -1] * (1 + dampnedChange))

    # don't change the price
    else:
      trend.append(trend[i - 1])

  return trend
```
{% endcode %}

The above code snippet represents the logic of how the peg is calculated. It uses the following variables.

* **pricesShortTerm:** A price feed that is used to represent the short-term trend of the underlying asset. In the current deployment, we use the 7-day moving average of the ETH/USD price feed.
* **pricesLongTerm:** A price feed that is used to represent the long-term trend of the underlying asset. In the current deployment, we use the 30-day moving average of the ETH/USD price feed.
* **startingPrice**: A starting price for the indicator. In the current deployment, this is set to 2$
* **dampeningFactor**: A dampening factor that dampens the indicator. A high `dampeningFactor` will cause the peg to capture more of the underlying collateral's appreciation. Vice-versa, a low `dampeningFactor` will cause the peg to capture less of the underlying collateral's appreciation. In the current deployment, the dampeningFactor is set at `10%`.

{% embed url="https://github.com/MahaDAO/gmu-oracle-contracts/blob/master/simulation/eth-24mo.ipynb" %}
A python notebook simulating the ETH Peg algorithm
{% endembed %}

## FAQs

### Who pays for the appreciation of ARTH?

The appreciation of `ARTH` is paid for by those who deposit collateral into the protocol. This means whenever `ARTH` appreciates against the US dollar, collateral providers who have opened loans and deposited collateral need to ensure that they are able to pay back their loan with the principal plus the appreciation (which behaves a bit like an interest fee).

### Is the appreciation of ARTH  similar to an interest fee or tax to borrowers?

Yes.&#x20;

While loans and lending protocol for `ARTH` is set to have 0% borrowing fees, the appreciation of `ARTH` behaves like an **indirect** interest fee or tax.

But since `ARTH` only appreciates if the underlying collateral appreciates, borrowers (in most cases) don't have to do anything if they are already exposed to the underlying collateral. Because `ARTH` appreciates at a fraction of how much the underlying collateral appreciates, the borrower still realizes a net gain even after paying for `ARTH`'s appreciation.

### Can the peg be influenced?

The peg can be influenced by only two major factors&#x20;

**Incentives via Governance**: Governance can decide to incentivize users who deposit a certain type of collateral, thereby influencing the collateral compositions of `ARTH`.

**Appreciation of the underlying collateral**: `ARTH`'s price is influenced by its underlying collateral (`ETH`)
