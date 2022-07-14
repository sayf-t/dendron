---
id: 7s14jsrbzri3fyy42v79z42
title: Stablecoins
desc: ''
updated: 1657786416781
created: 1657782301951
---

Stablecoins - always maintain the same value
- Define a currency of reference eg 1 stablecoin = 1 USD
- Usually defined as ERC20 tokens
- Use cases
  - Quote currency
    - Currency used as a reference, eg ` ETH/STABLECOINX -> 735 means
    - need 735 StablecoinX to get 1 ETH
  - Collateral
    - Needed by lending protocols
    - higher capital efficiency
  - Merchant payments
    - to accept payments

- Types of stable coins
  - Fiat-backed
    - "Real" currency eg USD, Euro etc
  - crypto-backed
    - Lock crypto to back stablecoins
  - Algorithmic
    - No reserve to back the value, rely on elastic supply to maintain price
    - when price is too:
      -high: SC will mint new tokens to bring price down
      -low: SC will burn some tokens to increase price
    - rely on Oracle SCs

---
## Links

- [Market cap of stablecoins](https://stablecoinindex.com/) (graph)
- [Market cap of stablecoins](https://www.coingecko.com/en/categories/stablecoins) (list)
- [Comprehensive list of stablecoins](https://defiprime.com/stablecoins)
[Hayek Money, The Cryptocurrency Price Stability Solution](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2425270) - This research paper was the major inspiration of Ampleforth, an algorithmic stablecoin
- [A Note on Cryptocurrency Price Stabilization: Seignoriage Shares](https://github.com/rmsams/stablecoins/blob/master/paper.pdf) - Another research paper that was quite influential for algorithmic stablecoins

