---
id: ie2b3pkjocay9pofiprl8jd
title: Wrapped Ether
desc: ''
updated: 1657772145373
created: 1657770870593
---

### Notes
- ETH is the native token, its genesis was prior to the implementation of the ERC20 standard
- Wrapping ETH allows parties to trade directly with alt tokens
- But all `wrapping` means is trading via a smart contract for an equal token called wETH (which can be `unwrapped` back to ETH)

### Julien's Notes
- DeFi has DEXes that allow for exchange
- ERC20 and Ether do not have the same API, so community introduced wETH
- 1ETH = 1 wETH
- when sending ETH, smart contract will mint wETH and send it back; and vice versa.

### Julien's demo

```solidity

pragma solidity ^0.7.3;

// Import the openzepplin contracts
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract Weth is ERC20 {
  constructor() ERC20('Wrapped Ether', 'WETH') {}

  function deposit() external payable {
    _mint(msg.sender, msg.value);
    // function already in OZ
    // specify the address of the sender of the transaction
  }

  function withdraw(uint amount) external {
    require(balanceOf(msg.sender) >= amount, 'balance too low');
    _burn(msg.sender, amount);
    // another method provided by the OZ implementation of ERC20
    msg.sender.transfer(amount);
  }
}

```

---
## Links
[Official smart contract](https://etherscan.io/address/0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2) of wrapped Ether on mainnet
[Official Documentation](https://weth.io/)