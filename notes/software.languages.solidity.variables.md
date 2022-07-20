---
id: 9zd4i83yed6x0jpsuexsgoe
title: Variables
desc: ''
updated: 1658212151677
created: 1657942568516
---

## Default values

![](./assets/images/solidity-default-values.png)

There are 3 types of variables in Solidity:
- local
  - declared inside a function
  - not stored on the blockchain
- state
  - declared outside a function
  - stored on the blockchain
- global (provides information about the blockchain)

```solidity
pragma solidity ^0.8.13;

contract Variables {
  // State variables
  string public text = "Hello";
  uint public num = 123;

  function doSomething() public {
    // Local variables
    uint i = 456;

    // Global variables
    uint timestamp = block.timestamp; // Current block timestamp
    address sender = msg.sender; // address of the caller
  }
}

```