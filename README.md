# Solidity Token

This Solidity program is a simple token creation contract that demonstrates the basic functionality of token minting and burning on the Ethereum blockchain. It provides a good starting point for those who want to explore the basics of smart contract development using Solidity, especially in the context of creating custom tokens.

## Description

This contract, written in Solidity, implements a basic token system called the LAMBDA token (abbreviation: LBA). The contract has functions to mint new tokens (increasing the supply) and burn tokens (decreasing the supply). The contract also tracks the total supply of tokens and provides a way to check the balance of any address.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract myToken {

    // public variables here
    string public tokenName = "YENDOR";
    string public tokenAbbrv = "YEN";
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
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the compiler version is set to 0.8.18 or any compatible version, and then click "Compile myToken.sol.".

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once deployed, you'll see the contract instance in the "Deployed Contracts" section. You can now interact with the mint and burn functions: Use the *mint* function to create new tokens for any Ethereum address. Use the *burn* function to destroy tokens from an address, ensuring the balance is greater than or equal to the amount to be burned.
## Authors

Metacrafter Earl Rodney N. Escario
## License

This project is licensed under the MIT License - see the LICENSE.md file for details
