# Basket-backed stablecoins

A [recent paper](https://www.bis.org/publ/work905.pdf) by the Bank for International Settlements outlined the current state of stablecoins, the concept of "global stablecoins" such as that of Facebook's Libra and the challenges and risks they pose in terms of hindering the ability of financial authorities' around the world to properly monitor and conduct anti-money laundering and counter-terrorism financing activities.

![](../.gitbook/assets/image%20%2828%29.png)

In this section we will outline the concept of the Libra basket-backed stablecoin so as to build some intuition and context for when we introduce the ARTH stablecoin.

Libra is a permissioned blockchain-based payment system whose stablecoin's value is linked to a basket of global reserve currencies such as the USD, GBP, EUR & JPY. 

The reason why it is defined as a "permissioned" blockchain is because the validator nodes which form part of the network are a private group of 30 or so companies called the "Diem Association". All major policy decisions will require the consent of two-thirds of the Diem Association Council’s representatives. Each of the association’s members will have one council member, including Facebook, which will also have only one vote. The association is currently made up of notable blockchain venture capital firms, as well as a number of other prominent technology startups such as Lyft, Shopify & Uber:

This model is in contrast to the Bitcoin or Ethereum networks whereby node operators are public and any entity or individual can run a node. In other words, Diem's blockchain is a centralized blockchain. Libra have however stated that their goal is to move to a public permissionless blockchain over time.

**Libra 2.0 features a 3-layer architecture;**

1. Layer 1 is the value-backing of two distinct types of stablecoins;

* Single-currency stablecoins \(USD, GBP, EUR, SGD\), referred to as Libra$, Libra€ etc \(similar to tokenized or wrapped versions of BTC\)
* Global stablecoin \(LBR\) - a basket of the above single-currency stablecoins

2. Layer 2 is the Libra blockchain - the wholesale payment system which makes stablecoins available to Facebook-specific payment service providers and e-wallet providers

3. Layer 3 - where single-currency stablecoins and LBR are made available to other external clients and wallets

**How does the Libra Reserve work?**

In the Libra Reserve \(a traditional asset-based value guarantee for single-currency stablecoins\), custodian banks hold assets on behalf of the Libra Association backing the single-currency stablecoins. 

The asset backing would be composed as follows;

* Over 80% are to be invested in short-term securities \(up to 3 months remaining maturity\) issued by liquid sovereigns with low credit risk \(i.e. A+ rating from S&P and A1 from Moody’s, or higher\). 
* The remainder is to be held in cash, with overnight transfers into Money Market Funds \(MMFs\). The MMFs must invest in short-term liquid sovereign debt \(up to 1 year remaining maturity\) with low credit risk.

Addressing currency risk: The Libra white paper notes that there will be no currency risk as the currency composition of assets will match the composition of outstanding single-currency stablecoins. The Libra reserve has provisions to address emergencies such as rapid outflows of funds during market turmoil. The Libra reserve can temporarily halt conversion or apply haircuts. 

The second tier of Libra 2.0 is a DLT-based global stablecoin. Custodian banks use their digital signature to cryptographically sign their guarantee into the public Libra Blockchain. Once these value guarantees are signed into the Libra Blockchain, LBR is a smart contract combining several single-currency stablecoins into a basket of currencies. 

For every LBR that is created, the smart contract “locks in” the respective amount of single-currency stablecoins on the Libra Blockchain. In terms of composition of LBR, the white paper mentions as an example;

* 50% weight for Libra$
* 18% for Libra€
* 11% for Libra£
* 21% - unknown

There are other projects such as Reserve Protocol whose long-term goal is to transition to a basket of assets, for comparisons between ARTH & Reserve Protocol please navigate to the section titled "[How is ARTH different to other stablecoins?](../arth-201/arth-vs-other-stablecoins.md)

_Source:_ [_https://www.bis.org/publ/work905.pdf_](https://www.bis.org/publ/work905.pdf)\_\_

