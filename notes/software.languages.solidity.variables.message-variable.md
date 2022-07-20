---
id: 0ptcucdlrtmf2pfm7ghv2za
title: Message Variable
desc: ''
updated: 1658209389833
created: 1658208987529
---

Global variable that can be used anywhere in code - Contains transaction data that was sent to the contract
```solidity

msg.sender // sender of the message
msg.value // number of ether sent in Wei unit
msg.data // calldata
msg.sig // first four bytes of calldata - called the function selector - EVM says which function to execute on the contract

```

### How are the first four bytes of calldata calculated?

```solidity
// take the function name and parameter types
bytes("transfer(address,uint256)")

// then calculate the keccak246 of that
keccak256(bytes("transfer(address,uint256)"))

// then from the result, take the first 4 bytes
bytes4(keccak256(bytes("transfer(address,uint256)")))


```