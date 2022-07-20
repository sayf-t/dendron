---
id: c002b1vy392fksvbq2emmcc
title: Mapping Type
desc: ''
updated: 1658212606839
created: 1658210591070
---

Default value: an empty mapping

- They are like tables! 
- And like hash tables which map keys to values
- allows for efficient **storing and reading of data**!
- no length
no keys

![](./assets/images/solidity-mapping.png)

Throwing in some keccak256 (the hash function part of EVM)...
![](./assets/images/solidity-mapping2.png)
- first calculate the hash
- then read the value

```solidity
// mapping that maps to another mapping
// just means MULTIPLE COLUMNS

mapping(address => mapping (bool => uint256)) myMapping;

```

![](./assets/images/solidity-mapping3.png)

If mapping is `public`, Solidity will automatically create public view function of same name.

`function myMApping(address param) public view returns(uint256);`

Mappings can only be storage - they cannot be parameters of return values of public functions, but can be passed as parameters for internal functions if needed.