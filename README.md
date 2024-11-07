# My Token

This project is a basic token contract created in Solidity. The purpose of this project is to demonstrate the creation of a smiple token contract that maps addressess to balance (address => uint) and functions allows for token minting and burning

## Description

This program is a simple contract written in Solidity, a programming language for developing smart contracts on the Ethereum blockchain. The contract has three public variables that store the details about the coin (Token Name, Token Abbrv., To  tal Supply), mapping of addresses to balances (address => uint), and two functions;
- **Mint**: a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance 
           of the “sender” address by that amount
- **Burn**: a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It 
           will then deduct the value from the total supply and the balance of the “sender”.
  Lastly, the burn function has a conditional statement that ensures that the balance of the "sender" is greater than or equal to the amount that is supposed to be burned.
  

## Getting Started

### Installing

* To download the program, Clone this repository.


### Executing program

*To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
* Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension e.g (e.g., MyToken.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.27;


contract MyToken {

    // public variables here
    string public tokenName = "DOGS";
    string public tokenAbbrv = "DGS";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    } 

    // burn function
    function burn (address _address, uint _value) public {
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.27" (or another compatible version), and then click on the "Compile MyToken.sol" button.
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.
Once the contract is deployed, you can interact with it. Click on the "MYTOKEN" contract in the left-hand sidebar, and then click on the "mint" function and insert the required parameters i.e the address(copy your eth address above the functions), the value to be added. After minting click on the totalSupply variable to see if it has been added. Finally, You can interact with other functions and other variables.



## Authors

Mubarak AKA elmuby

