---
description: This section talks about the ARTH peg
---

# What is ARTH pegged to?

Because stablecoins are almost always pegged to a target price, it is ideal for them to revolve around that price. Most stablecoins are pegged to 1 USD  or another fiat currency (like Japanese Yen, Chinese Yuan, etc).&#x20;

However, ARTH is price pegged to the algorithmic price-feed called as the global measurement unit (or the GMU). For simplicity purposes, ARTH's initial price was set at **2 USD worth of GMU,** signifying the rise in inflation amongst other things.

The goal of the algorithmic peg is to achieve stability whilst at the same time slowly appreciate in value.

![A sample simulation of the GMU indicator](<.gitbook/assets/image (9).png>)

In various simulation, it was found that the GMU remained relatively stable in moments when the market turned bearish but started to appreciate ever so slightly whenever the market turned bullish.

## How does the GMU work?

The basic idea of the GMU is to capture the growth/appreciation of an underlying asset without causing too much volatility. In this case, the underlying asset is ETH.

To do this it uses two moving averages. A 7 day moving average to understand the short term price trend of the underlying asset (which is mainly used to understand when to stop the appreciation). And a 30 day moving average which is used to understand the long term price trend of an underlying asset (which is mainly used to understand how much to appreciate the price by).

If both the 30 day and 7 day moving averages are in an upwards trend, then the indicator appreciates the peg by a fraction of the appreciation of the 30 day moving average.

{% code title="indicator.py" %}
```python
# https://github.com/MahaDAO/gmu-oracle-contracts/blob/master/simulation/indicator.py
def arth_indicator(pricesLongTerm, pricesShortTerm, startingPrice,  
  longTermDuration = 30, dampeningFactor = 0.1):
  '''
  An indicator to algorithimatically calculate ARTH's price
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

The above code snippet represents logic on how the GMU is calculated. It uses the following variables.

* **pricesShortTerm:** A price feed that is used to represent the shot-term trend of the underlying asset. In the current deployment, we use the 7 day moving average of the ETH/USD price feed.
* **pricesLongTerm:** A price feed that is used to represent the long-term trend of the underlying asset. In the current deployment, we use the 30 day moving average of the ETH/USD price feed.
* **startingPrice**: A starting price for the indicator. In the current deployment, this is set to 2$
* **dampeningFactor**: A dampening factor that dampens the indicator. A high `dampeningFactor` will cause the GMU to capture more the underlying collateral's appreciation. Vice-versa, a low `dampeningFactor` will cause the GMU to capture less of the underlying collateral's appreciation. In the current deployment, the dampeningFactor is set at `10%`.

{% embed url="https://github.com/MahaDAO/gmu-oracle-contracts/blob/master/simulation/eth-24mo.ipynb" %}
A python notebook simulating the GMU algorithm
{% endembed %}

## FAQs

### Who pays for the appreciation of ARTH?

The appreciation of ARTH is paid for by those who deposit collateral into the protocol. Which means whenever ARTH appreciates against the US dollar, collateral providers who have opened loans and deposited collateral need to ensure that they are able to payback their loan with the principal plus the appreciation (which behaves a bit like an interest fee).

### Is the appreciation of ARTH  similar to an interest fee or tax to borrowers?

Yes.&#x20;

While loans and lending protocol for ARTH is set to have 0% borrowing fees, the appreciation of ARTH behaves like an **indirect** interest fee or tax.

But since ARTH only appreciates if the underlying collateral appreciates, borrowers (in most cases) don't have to do anything if they are already exposed to the underlying collateral. Because ARTH appreciates at a fraction of how much the underlying collateral appreciates, the borrower still realizes a net gain even after paying for ARTH's appreciation.

### Can the peg be influenced?

The peg can be influenced by only two major factors&#x20;

**Incentives via Governance**: Governance can decide to incentivize users who deposit a certain type of collateral thereby influencing the collateral compositions of ARTH.

**Appreciation of the underlying collateral**: ARTH's price is influenced by its underlying collateral (ETH)
