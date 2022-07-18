---
id: lmu46m0f23xyyj5b7fasx4g
title: Immutable
desc: ''
updated: 1657943529873
created: 1657943391135
---

- Immutable variables are like constants.
- Values of immutable variables can be set inside the constructor but cannot be modified afterwards.

```solidity
contract Immutable {
    // coding convention to uppercase constant variables
    address public immutable MY_ADDRESS;
    uint public immutable MY_UINT;

    constructor(uint _myUint) {
        MY_ADDRESS = msg.sender;
        MY_UINT = _myUint;
    }
}

```
