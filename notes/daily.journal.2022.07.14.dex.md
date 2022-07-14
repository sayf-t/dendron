---
id: o02ynotfr2idi07301r9d8m
title: Dex
desc: ''
updated: 1657790306379
created: 1657787709280
---

- DEX = SC where investors can trade their tokens in a decentralised way
![](./assets/images/dex1.png)

- No risk of having your tokens frozen
![](./assets/images/dex2.png)
- old forms of DEXes used orderbooks where
  - people who bring liquidity are called "market makers"
  - Market makers use buy/sell limit orders to trade around
    - buy low; sell high, make profit
  - Problems of being a market maker:
    - needed lots of capital
    - needed to act quickly as markets changed
    - difficult to bring liquidity to these exchanges with an orderbook esp for small coins that hardly attract big market makers
![](./assets/images/dex3.png)

- Needed to find an alternative to orderbooks
- Vitalik released a paper that introduced the idea of an AMM
  - anybody could become an AMM
  - just have to send tokens to a SC and earn trading fees
  - how does it work?
    - Instead of "market makers" we usually refer to liquidity providers
    - AMM works with liquidity pools eg ETH/DAI

    ![](./assets/images/dex4.png)
    - the ratio of the two assets determine the current price
    - LP sends the 2 assets to the SC of the Liq pool. 
    - Need to be the required proportion
    - Liq pool SC will send back LP tokens in exchange
    ![](./assets/images/dex5.png)
    - Then a trader uses the DEX swaps one asset of the pool against the other, eg trader sends DAI + trading fees to the pool and gets ETH in exchange
    ![](./assets/images/dex6.png)
    - When the Liq provider wants to get back his/her money: 
      - needs to send back the LP token and get back the DAI/ETH + trading fees 
      - trading fees are a function of the time spent in the pool, amount invested as a weight of total liquidity
      ![](./assets/images/dex7.png)
      - big question is how is the price determined?
        - SC uses the **constant product formula**
        ![](./assets/images/dex8.png)
        - visually can be represented as this curve
        ![](./assets/images/dex9.png)
        - eg this is the equation that must be satisfied:
        ![](./assets/images/dex10.png)
      - difference in prices?
        - can be due to slippage
        ![](./assets/images/dex11.png)
      - Impermanent Loss?
      ![](./assets/images/dex12.png)
        - holding assets vs providing liq to an AMM can result in a loss due to a rapid change in price
        ![](./assets/images/dex13.png)


---

# Links

["On Path Independence" of Vitalik Buterin, foundational blog post for AMM](https://vitalik.ca/general/2017/06/22/marketmakers.html)
