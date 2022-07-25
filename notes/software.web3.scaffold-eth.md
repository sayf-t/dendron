---
id: l30r3iar5w0ftxxx87ei0kz
title: Scaffold Eth
desc: ''
updated: 1658634171986
created: 1658544998981
---

# Scaffold-eth: A brilliant localhost environment to get started with Solidity!

#solidity #learning #ethereum

After falling into a Youtube rabbit hole of web3 goodies, I stumbled on a video featuring industry dev-rel titans Patrick Collins, Nader Dabit and Austin Griffiths (check it out [here](https://youtu.be/2VMvfmPG5jg)!) where they're just bouncing ideas off each other, sharing their thoughts, opinions and news.

At one point I heard names like `Scaffold-eth` and `Ethereum Speed Run` being tossed around so I decided to check them out, and these are initiatives by Austin (and his team?) - and what I found blew my mind! 

Once you set up `Scaffold-eth` you can make changes to the solidity code and, upon a `yarn deploy` and hot-reload, see the results of a deployed smart contract.

As someone who learns most effectively with visuals accompanying my coding, this was a refreshing break from always imagining things in my head, trying to keep them straight as to how my code changes were affecting variables etc.


## Getting started with Scaffold-eth
Here's how to get set up with `Scaffold-eth`:

1) Head to https://github.com/scaffold-eth/scaffold-eth and, with your terminal, clone the repo into a new folder:
```
git clone https://github.com/scaffold-eth/scaffold-eth.git
```

2) This part has you opening 3 separate terminals for starting up the:  
  a)   Hardhat chain:
  ```
  cd scaffold-eth
  yarn install
  yarn chain
  ```
  b)  Front-end:
  ```
  cd scaffold-eth
  yarn start
  ``` 
  c) Contract deployment:
  ```
  cd scaffold-eth
  yarn deploy
  ```