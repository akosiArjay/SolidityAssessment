# SolidityAssessment

This code is a Solidity smart contract for a simple token, which allows for minting and burning of tokens. It includes public variables to store the token name, abbreviation, and total supply, as well as a mapping of addresses to balances. The mint function increases the total supply by a specified value and increases the balance of the "sender" address by the same amount, while the burn function decreases the total supply and balance of the "sender" address by a specified value, as long as the sender has enough tokens to burn. This contract can serve as a starting point for building more complex token contracts on the Ethereum blockchain.

## Description

This Solidity smart contract defines a simple token called "META" with a total supply and a mapping of addresses to balances. It includes two functions, mint and burn, which respectively increase and decrease the total supply and balance of the "sender" address. The burn function includes a check to ensure that the "sender" has enough tokens to burn. This code serves as a starting point for creating more complex token contracts on the Ethereum blockchain, which can be used for various purposes such as rewards or access control.

### Executing program

* Remix is an online Solidity IDE that you may use to run this application. To get started, go to https://remix.ethereum.org/.
* Create a new Solidity file in your development environment.
* Copy and paste the code for the MyToken contract into the new file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbry = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
       totalSupply += _value;
       balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public {
       if (balances[_address] >= _value) {
          totalSupply -= _value;
          balances[_address] -= _value;
       }
    }

}
```
* Compile the code by selecting "Solidity" as the compiler version and clicking "Compile".
* Deploy the contract by selecting "MyToken" from the dropdown menu in the "Deploy & Run Transactions" tab and clicking "Deploy". This will create a new instance of the contract on the blockchain.
* Once the contract is deployed, you can interact with it using the functions defined in the contract. For example, you can mint new tokens by calling the "mint" function and passing in the address and value of the tokens you wish to mint. Similarly, you can burn tokens by calling the "burn" function and passing in the address and value of the tokens you wish to burn.
* You can view the current balance of any address by calling the "balances" mapping with the address as the argument. This will return the current balance of tokens held by that address.
* You can view the current balance of any address by calling the "balances" mapping with the address as the argument. This will return the current balance of tokens held by that address.

## Authors

NTC Scholar Arjay Rafael

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
