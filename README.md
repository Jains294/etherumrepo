# ETH PROOF: Beginner EVM Course
The Ethereum Proof: Beginner EVM Course is designed to teach beginners how to develop smart contracts using the Ethereum Virtual Machine.

## Description
 The course covers various topics such as:

1. Introduction to Ethereum and Smart Contracts
2. Solidity programming language
3. Understanding the EVM architecture
4. Writing, deploying, and interacting with smart contracts
5. Testing and debugging smart contracts

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public name_token="metacrafter";
    string public  abrev_token="meta";
    uint public totalsupply=0;

    // mapping variable here
mapping(address =>uint)public balances;

    // mint function
    function mint(address _address,uint _value)public {
        totalsupply += _value;
        balances[_address]+=_value;
    }

    // burn function
   function burn(address _address,uint _value) public {
    if(balances[_address] >= _value) {
     totalsupply-=_value;
    balances[_address]-=_value;
    }
   }
}
* Clone Repository: Clone the repository containing the Solidity file onto your local machine.

* Compile Contract: Compile the Solidity smart contract using a Solidity compiler such as Hardhat or Remix.

* Deploy Contract: Deploy the compiled contract to a blockchain network. Ensure that you have a suitable Ethereum development environment set up.

* Interact with Contract: Use a tool like Remix or web3.js to interact with the deployed contract. You can mint, burn, and transfer Nectar tokens as desired.

## Help

For any assistance or queries, feel free to reach out to the contract author via [email](akshat.bal2003@gmail.com).

## Author
Akshat Jain

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
