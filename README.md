# ETH-AVAX_module_3 Creating A Token with ERC20

This Solidity program is a simple program that demonstrates the use of erc20 contracts for making fungible tokens by yourself and use different functions for the tokens using interface available in the erc20 contracts.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. In this contract we have made a token and provided some fuctionalities to the users like minting the the tokens(by owner only), transfer the tokens or just burn the tokens with different permssions for different functions or tasks. This program serves as a simple and straightforward introduction to use of erc20 contracts and interfaces avaialable, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

Tokens made on Solidity using the erc20 smart contracts are basically used with help of Remix Ethereum ONLINE COMPILER. link to the compiler : https://remix.ethereum.org
On the remix compiler wht you have to do is that Create a new file by clicking START CODING button available on the page it will open you a new file. Go to your file with.sol extension and rename it as per your choice.
```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

contract tokenn is ERC20 {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) {
        
    }
    address owner=0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    modifier mint_by_owner(){
      require(msg.sender==owner,"Minting allowed to owner only");
      _;
    }
    function mint(address recieve, uint amount)public mint_by_owner{
      _mint(recieve,amount);
    }
    function burn(address account,uint amount)public{
      _burn(account, amount);
    }
    function transfer(address send,address rec,uint amount) public{
    _transfer(send, rec, amount);
    }
}


```

 1. Define Solidity version
 2. Import a file from github to use erc20 contracts "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol"
 3. Make a contract for the token making process using the constructor function available through the interface.
 4. Use the constructor for Nmaing your token and giving it a symbol.
 5. Then make a function mint to mint the tokens. But we wanted to allow owners of the contracts only to mint so what we did is we made a modifier that ensures that onle owner is calling the mint function.
 6. Declare Burn function make it public as well as simply without use of any modifier just use _burn from the contracts.
 7. Similar to burn declare the transfer function and use _transfer function from erc20 contract.
 8. That's it now your token can be minted by owner, transferred and burnt by anybody.


## Authors

Hardik 
hardikxibscience238@gmail.com
LinkedIn : https://www.linkedin.com/in/hardik-taneja-b0030527a/?lipi=urn%3Ali%3Apage%3Ad_flagship3_feed%3B4F%2Fj7bf6QjeFo%2Bb7zqYXHw%3D%3D
X: @hardik_26629
